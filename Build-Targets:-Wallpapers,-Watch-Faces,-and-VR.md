## Build Targets

New in v0.5.0, APDE lets you build wallpaper, watch face, and VR sketches in addition to regular apps. Most sketches are automatically compatible with these different targets, so you can start building them right away.

To change targets, press the new button to the right of the "run" button; this is the target selection button. There are four options: app, wallpaper, watchface, and VR.

Note that installing an app with the same package name overwrites the existing installed app, even if the existing app was built for a different target. For example, if you have a sketch that was already built as an app and then you build it as a wallpaper, the app will no longer be installed and the wallpaper will take its place. If you want both targets around, you need to change the sketch name or package name. There may be better ways to handle this type of situation in the future.

Check out the Android Processing [reference](http://android.processing.org/reference/index.html) and [tutorials](http://android.processing.org/tutorials/index.html) for information about special features in these targets. Note that implementing some of these features will break your sketch in other targets. For example, using watch face-specific features will crash your sketch in any other target. Also note that APDE does not require you to explicitly import the Processing VR library, and the VR renderer is automatically added to VR sketches.

Wallpapers, watch faces, and VR all have folders under Examples > Topics that may be interesting.

This feature was driven by GSoC '18. Special thanks to Sara di Bartolomeo, Andres Colubri, and the Processing Foundation!

### Wallpapers

You can run any sketch as a live wallpaper and set it as your home screen background.

Almost all sketches will work right out of the box, but some sketches that rely on specific activity features will fail because wallpapers do not run in activities.

### Watch Faces

You need a Wear OS watch (formerly Android Wear 2.0) in order to run watch faces. Install the APDE wear companion app (listed as "APDE - Android Processing IDE") from Google Play on your watch and make sure that the watch and phone are connected. APDE will only let you run a sketch as a watch face if it detects the wear companion app on a connected watch.

Watch faces are not installed the same way as regular apps due to Wear OS restrictions (the platform does not allow you to sideload apps without an adb connection). Instead, the wear companion app loads the sketch into its watch face and displays it. Consequently, you can only ever run one sketch at a time on your watch. If you want multiple sketches to pick from, you can export them (Tools > Export Signed Package, make sure to pick the watch face target) and then sideload them onto your watch from a computer.

### VR

VR supports the Google VR platform, i.e. the Carboard and Daydream headsets. Daydream-specific functionality (the laser pointer) is not currently supported by Android mode, but sketches run well with both headsets.

Note that your phone must support the Google VR library. Tablets and some phones may not have this capability.

VR sketches must use a 3D renderer (P3D). 2D sketches will still build but will likely not display anything. There are a number of 3D examples in the downloaded examples repository, in particular Demos > Graphics is a good place to start.

If you don't have a headset, VR also includes a "magic window" mode that works standalone. This is Processing's MONO renderer (as opposed to the default STEREO). You can specify this explicitly, but APDE automatically adds the default renderer (STEREO) to sketches when building for the VR target. You can change the default renderer from STEREO to MONO in Settings > Build > Default VR Renderer. This way all 3D sketches run in VR will automatically use MONO.

A quick warning: In my testing, magic window mode was very difficult to escape. Normal VR sketches (using STEREO) feature an "X" in the corner to close the sketch, but magic window sketches lack this mechanism and VR tends to take over the phone. My phone lacks hardware back, home, and recent apps buttons, so I was only able to quit magic window by power-cycling or triggering "Ok, Google". This seems to be the fault of the Google VR library itself. Just proceed with caution, but if you can find a way to reliably quit the sketch, then you should be fine.