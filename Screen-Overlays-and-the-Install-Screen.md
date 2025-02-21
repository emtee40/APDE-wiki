## AKA "Why can't I press the install button?"

**Situation**: You have run a sketch from APDE and the install screen with the "install" and "cancel" buttons appears. However, nothing happens when you try to press the install button.

**TL;DR**: You need to temporarily disable any screen dimming/blue light filter app that you have installed on your phone, including Lux, Twilight, or any similar screen filter app. The app must be disabled when you press the install button.

**Explanation**: There are many different types of screen filter apps that do things from providing more fine-grained control over system brightness to reducing the amount of blue light emitted by the screen. All of these apps work by drawing a translucent rectangle over the entire screen, including the currently visible app, and thus require the "draw over other apps" permission.

As a security feature, Android prevents potentially dangerous actions from being performed while another app is drawing over the screen because a malicious such app could trick the user into performing a harmful action to gain control of the device. These actions include sideloading APK files (such as installing APDE sketches) and changing app-level permissions in Settings on Android 6.0+ (Marshmallow). In the latter case, the system tells you "screen filter detected" upon trying to change permissions with a screen filter enabled, but in the former, there is no way to know why pressing the install button doesn't work. Note that the install screen described above is not part of APDE, but is created by the Android system, so APDE has no control over this behavior. (If APDE did, then that would have terrible security implications.)

Therefore, in order to install APDE sketches, you must temporarily disable your screen filter app. You do not need to uninstall the app and you may have it enabled on every screen except for the install screen.

If you don't know which app is acting as a screen filter, then you can go to Settings > Apps > Advanced/More (in the top right) > Draw over other apps (or something to that effect). (Note that the exact path varies from device to device). From here, selectively disable the ability to draw over other apps until you discover which app is causing the issue. Note that, theoretically, multiple apps could be simultaneously drawing a screen overlay, in which case you would have to disable all of them.

There is, unfortunately, no other workaround for this issue, and the cause is entirely outside of APDE's control.