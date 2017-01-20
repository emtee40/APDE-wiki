APDE (Android Processing Development Environment) is a [Processing](https://processing.org/) IDE for creating and running sketches on Android devices. You can download APDE from [Google Play](https://play.google.com/store/apps/details?id=com.calsignlabs.apde) or the [releases page](https://github.com/Calsign/APDE/releases).

New here? See [Getting Started](https://github.com/Calsign/APDE/wiki/Getting-Started) for the basics.

APDE is developed by William Smith (aka Calsign or CalsignLabs) and is not supported by the Processing Foundation.

## FAQ

### How do I install a library?

To install a contributed library (libraries that are not included in the desktop Processing download), please see [Installing Contributed Libraries](https://github.com/Calsign/APDE/wiki/Installing-Contributed-Libraries).

If you are looking to use a core library (including the Serial library), then see below...

### Where is the Serial library (or any other core library)?

APDE does not support any of the core libraries, including Serial, Network, Video, and Sound.

However, there is a contributed library, [Processing-Android-Serial](https://github.com/inventit/processing-android-serial), that claims to port the Serial library to Android mode. I have not tested this personally, but some users have reported that it works.

I do not know of any ports for the other core libraries, but there may be alternatives for them as well.

APDE cannot support core libraries because APDE uses *Android mode* Processing, not Java mode. All of the core libraries are part of Java mode and are thus available neither in desktop Android Mode nor APDE. Android mode cannot support these libraries because they are generally dependent upon hardware or other native libraries that are simply not present in Android.

### How do I export?

To export a signed APK file that can, for example, be published to Google Play, please see [Exporting as a Signed Package](https://github.com/Calsign/APDE/wiki/Exporting-as-a-Signed-Package).

### Why can't I press the install button?

Please see [Screen Overlays and the Install Screen](https://github.com/Calsign/APDE/wiki/Screen-Overlays-and-the-Install-Screen).