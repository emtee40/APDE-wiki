This wiki is not yet fully operational. The information that would otherwise be provided here is currently located in the main README file. I will gradually add pages here until this becomes a real wiki.

## FAQ

### How do I install a library?

To install a contributed library (libraries that are not included in the desktop Processing download), please see [Installing Contributed Libraries](https://github.com/Calsign/APDE/wiki/Installing-Contributed-Libraries).

If you are looking to use a core library (including the Serial library), then see below...

### Where is the Serial library (or any other core library)?

APDE does not support any core libraries, including Serial.

However, there is a contributed library, [Processing-Android-Serial](https://github.com/inventit/processing-android-serial), that claims to port the Serial library to Android mode. I have not tested this personally, but some users have reported that it works.

I do not know of any ports for the other core libraries, but no one has asked about them before, so there may be alternatives for them as well.

APDE cannot support core libraries because APDE uses *Android mode* Processing, not Java mode. All of the core libraries are part of Java mode and are thus available neither in desktop Android Mode nor APDE. Android mode cannot support these libraries because they are generally dependent upon hardware or other native libraries that are simply not present in Android.

### How do I export?

To export a signed APK file that can, for example, be published to Google Play, please see [Exporting as a Signed Package](https://github.com/Calsign/APDE/wiki/Exporting-as-a-Signed-Package).