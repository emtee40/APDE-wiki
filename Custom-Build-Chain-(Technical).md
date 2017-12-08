APDE uses a custom build chain for running sketches. It differs from the desktop Android mode's ANT build primarily in that it uses Eclipse's compiler (ECJ) instead of the Java compiler (JAVAC). When you press the run button, this is what happens behind the scenes:

 - ANTLR Preprocessor (Android mode Processing) - basically the same as the PDE
 - AAPT (Android SDK) - creates R.java and bundles the resources
 - ECJ (Eclipse) - compiles resulting source files and spits out errors to the console
 - DX Dexer (Android SDK) - converts compiled .class files to Android's .dex (Dalvik EXecutable) files
 - DX Merger (Android SDK) - merges all of the .dex files into one big .dex file
 - APKBuilder (Android SDK) - creates an APK (Android Package) file from the resources and the DEX files
 - ZipSigner ([library](https://code.google.com/p/zip-signer/)) - zipaligns the APK and signs it with a debug certificate

For those interested, the build process is located in the [`build()`](https://github.com/Calsign/APDE/blob/master/APDE/src/main/java/com/calsignlabs/apde/build/Build.java#L380) method of `com.calsignlabs.apde.build.Build.java` (this isn't the cleanest code, but it's there).

Note: Libraries are dexed during the installation process to speed up build times.