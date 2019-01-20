 > Note: Preview mode is a feature is new in v0.5.1.

### Basics

With preview mode, you don't need to reinstall the sketch every time you run it. Instead, you install the sketch previewer once, and every subsequent run does not need to be installed. Build times are significantly faster than regular app builds.

Preview mode is available from the target selection dropdown (to the right of the run button). The other targets are app (all builds prior to APDE v0.5.0), wallpaper, watch face, and VR. To run a sketch in preview mode, select "Preview" from the dropdown and then press run.

### Sketch Previewer

You must install the sketch previewer once in order to run sketches in preview mode. Once you install the sketch previewer, you can run any sketch as many times as you want without reinstalling. The exception to this rule is if you run a sketch that requires additional permissions. For example, if you run a sketch that requires the camera permission, you must reinstall the sketch previewer in order to give it the camera permission. Once the sketch previewer has been reinstalled with the new permission, any sketch using the added permission can be run indefinitely without reinstalling. Eventually you should accumulate all of the permissions that you want and you will never need to reinstall.

The sketch previewer adds more permissions on the fly because it was deemed undesirable to give all possible permissions at first install - some users may be uncomfortable yielding all dangerous permissions at once. The reinstall is required because permissions can only be added at compile time. APDE actually recompiles the sketch previewer on the fly when you add permissions, but this process should be totally seamless.

The sketch previewer starts with the permissions INTERNET, ACCESS_NETWORK_STATE, and VIBRATE by default because these permissions are innocuous (and none are marked dangerous by the Android system). This means that all sketches can use these permissions without having to reinstall the sketch previewer.

If you want to customize the sketch previewer, you can do so from Settings > Build > Preview Mode. You can reinstall the sketch previewer and uninstall it from here. You can also select exactly which permissions are granted to the sketch previewer. When you finish picking permissions, you will be prompted to reinstall the sketch previewer in order to update its permissions. This way you have full control over which permissions the sketch previewer has access to.

### Build Process

Preview mode skips several steps of the build process: DX-Merge (merging dexes), APKBuilder (building apk), ZipSigner (zipaligning and signing APK), and installation. The only significant remaining steps are AAPT (assets), ECJ (compilation), and DX-Dex (dexing), so the build process is much more streamlined. On my Galaxy S9+, the entire process takes less than two seconds. On a lower end phone the process should still be a significant improvement over the regular app build.

### Technical Quirks

The sketch previewer works by loading the sketch's class files and then executing them. This means that the sketch runs in an environment that is slightly different from a regular app.

The data folder works differently. For regular Android Processing apps, the data folder gets packaged into the assets directory of the APK, and this cannot be changed at runtime. To get around this, the sketch previewer copies the sketch's data folder into its private internal storage. Processing's default load function first checks assets and then checks the internal storage, so most methods of accessing files from the data folder should still work. However, if you access assets directly or use a library that accesses assets directly (which many libraries do), you will run into difficulties. If this happens, then you need to either run the sketch as a standard app or change the way that you access the data folder. APDE may have a better way of handling the data folder in the future.

The internal storage and shared preferences get cleared every time you run a sketch in preview mode. This means that if you intend to save state after re-running the app in preview mode, then you should do it elsewhere, such as on the external storage. This is done so that different sketches have a clean slate to work with, without the clutter that other sketches might leave behind.

There are numerous other small quirks. Most sketches will run perfectly fine, even if you save files or use permissions, but some edge-case sketches may break in preview mode. Most difficulties (beyond the data folder problems described above) should only arise if you are doing highly sophisticated or low-level things. In this case, either run the sketch as a normal app or change what you are doing. If you have a problem with a significant use case, please report it to me and I will update the information here and try to find a solution.