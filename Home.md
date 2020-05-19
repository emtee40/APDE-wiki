APDE (Android Processing Development Environment) is a [Processing](https://processing.org/) IDE for creating and running sketches on Android devices. You can download APDE from [Google Play](https://play.google.com/store/apps/details?id=com.calsignlabs.apde) or the [releases page](https://github.com/Calsign/APDE/releases).

New here? See [Getting Started](https://github.com/Calsign/APDE/wiki/Getting-Started) for the basics.

More documentation:

 - [Installing Contributed Libraries](https://github.com/Calsign/APDE/wiki/Installing-Contributed-Libraries)
 - [Exporting as a Signed Package](https://github.com/Calsign/APDE/wiki/Exporting-as-a-Signed-Package)
 - [Build Targets - Wallpapers, Watch Faces, and VR](https://github.com/Calsign/APDE/wiki/Build-Targets:-Wallpapers,-Watch-Faces,-and-VR)
 - [Features Overview](https://github.com/Calsign/APDE/wiki/Features-Overview)
 - [Supported Devices](https://github.com/Calsign/APDE/wiki/Supported-Devices)
 - [Required Permissions (for APDE itself)](https://github.com/Calsign/APDE/wiki/Required-Permissions)

APDE is developed by William Smith (aka Calsign or CalsignLabs). APDE is not a Processing Foundation project.

## FAQ

### Why does APDE ask to install apps from unknown sources?

You have pressed the run button and APDE has finished building the sketch, but you see a warning dialog telling you something along the lines of "Install blocked: For security, your phone is set to block installation of apps obtained from unknown sources."

Please see [Enabling Installation from Unknown Sources](https://github.com/Calsign/APDE/wiki/Enabling-Installation-from-Unknown-Sources).

### How do I install a library?

To install a contributed library (libraries that are not included in the desktop Processing download), please see [Installing Contributed Libraries](https://github.com/Calsign/APDE/wiki/Installing-Contributed-Libraries).

If you are looking to use a core library (including the Serial library), then see below...

### Where are the Serial, Network, Video, or Sound libraries?

APDE does not include any of the core libraries, including those listed above. However, there are some contributed libraries that should work in their place:

 - [processing-sound](https://github.com/processing/processing-sound) for Sound. [Download](https://github.com/processing/processing-sound/releases/download/v2.0.2/sound.zip)
 - [AndroidSerial](https://github.com/inventit/processing-android-serial) for Serial. [Download](https://github.com/inventit/processing-android-serial/releases/download/0.2.0/AndroidSerial-distribution.zip)
 - [video_android](https://github.com/omerjerk/processing-video-android) for Video. [Download](https://github.com/omerjerk/processing-video-android/releases/download/Release/video_android.zip)

APDE cannot support core libraries because APDE uses *Android mode* Processing, not Java mode. All of the core libraries are part of Java mode and are thus available neither in desktop Android Mode nor APDE. Android mode cannot support these libraries because they are generally dependent upon hardware or other native libraries that are simply not present in Android.

### How do I export?

To export a signed APK file that can, for example, be published to Google Play, please see [Exporting as a Signed Package](https://github.com/Calsign/APDE/wiki/Exporting-as-a-Signed-Package).

### Why can't I press the install button?

Please see [Screen Overlays and the Install Screen](https://github.com/Calsign/APDE/wiki/Screen-Overlays-and-the-Install-Screen).

### How do I use multitouch?

AKEric has two [blog](http://www.akeric.com/blog/?p=1411) [posts](http://www.akeric.com/blog/?p=1435) about multitouch that are helpful. Additionally, the example CalsignLabs/Drift implements multitouch and can serve as a reference.

### How do I fix "Parse Error: There is a problem parsing the package"?

APDE has finished building your sketch and it goes to install, but instead of the installer you see a dialog that says "Parse Error: There is a problem parsing the package". The following solution has been successful for a number of users: Go to Settings > Build and then disable "Build on Internal Storage" and enable "Keep Build Folder". If this doesn't work then please open an issue in this repository or send me an email.

### How do I show/hide the soft keyboard?

Please see [Showing or Hiding the Software Keyboard](https://github.com/Calsign/APDE/wiki/Showing-or-Hiding-the-Software-Keyboard).