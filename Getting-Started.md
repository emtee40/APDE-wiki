### For Processing users

APDE is based on Processing's [Android mode](http://android.processing.org/). There are some [minor differences](http://android.processing.org/reference/gone.html) between "normal" Java mode Processing and Android mode, but most sketches will not need to be changed for Android mode (especially beginner-level sketches).

### For those learning Processing

The Processing website has lots of great [tutorials](https://processing.org/tutorials/) and [examples](https://processing.org/examples/) for beginners. The [online reference](https://processing.org/reference/) is particularly useful for both newcomers and the experienced.

The reference is also available in APDE from Tools > Open Reference or by selecting "Find In Reference" from a highlighted keyword.

## Getting started with APDE

When you first launch APDE you are presented with an empty sketch. You can type some code, for example...

``
rect(100, 100, 200, 200);
``

...and press the run button, the right-facing arrow at the top of the screen, to build and launch the sketch. You will see some information being spit out in the console as the sketch builds.

 > Tip: You can long-press the message area (the gray bar between the code area and the console) to drag it, resizing both areas in the process.

Once the build has finished you will see an app install screen. APDE sketches run as full-fledged Android apps, so they must be installed like a normal app. (If you currently have installation from unknown sources disabled, then you will need to enable it from Settings. The installer should prompt you to do so if it is disabled.)

Now press "Open", and voila! You have run your first sketch! You can press the back button to return to APDE.

### The Sketchbook

The sketch that is created when APDE is first launched and as any sketches made with "New Sketch" in the menu are by default temporary sketches with a date-stamp name. Temporary sketches are never deleted (unless you delete them), but they are not very organized.

To make your sketch more permanent, you can select "Move to Sketchbook" from the menu. Sketches in the Sketchbook can be renamed and organized into folders. You can now rename your sketch with "Rename Sketch" in the menu.

### The sketch manager drawer

To load a sketch, press the three horizontal lines in the top left corner, swipe in from the left side of the screen, or select "Load Sketch" from the menu. This action will make the sketch manager drawer appear.

There are five top-level folders: Sketches, Examples, Library Examples, Temporary, and Recent. Sketches is your Sketchbook. Examples contains the four default examples or the entire repository if it has been downloaded. Library Examples has the examples for any libraries that you have installed. Temporary is all of the temporary sketches that haven't been moved to the Sketchbook yet. Recent is a list of your recent sketches, with the most recently opened first.

You can load a sketch from any of these folders by opening the folder and selecting the sketch (or example). To navigate up a level, press the ".." at the top of the sketch manager drawer.

> Tip: Within the Sketches folder, you can long-press a sketch to move it to a new sub-folder, rename it, or delete it by dragging the sketch to the corresponding icon at the bottom of the screen. You can organize your Sketchbook by moving sketches into different sub-folders. You can also long-press temporary sketches to move them to the Sketchbook or delete them.

### Examples

If you are just getting started with APDE, you might want to experiment with some of the examples at this point in time.

When you first started APDE, you should have seen a dialog asking you to download the examples repository if you were on a Wi-Fi network. If you chose to download the repository then you now have a large set of examples to work with. If you didn't download the repository then you only have the four default examples, but you can still choose to download the repository later.

If you would like to download the repository even over mobile data, then go to Settings > General > Examples Updates and select "Over Mobile Network". Now restart APDE and the dialog should appear. (Alternatively you can press "Re-download Examples Now" to download the examples without restarting and the dialog.)

Updates to the examples repository will be released periodically, at which point in time the update dialog will re-appear.

### Tabs

You can create multiple tabs within your sketch to organize your code, just as you can in the desktop Processing. To create a new tab, press the current tab at the top of the screen (labelled "sketch" by default) and selected "New Tab". Similarly, you can choose "Rename Tab" or "Delete Tab" to rename or delete the current tab, respectively.

Separate tabs are stored as separate .pde files in the sketch folder.

> Tip: You can also load .java files in the sketch folder as separate tabs, but it is not yet possible to create .java files from within APDE.

### Debugging

When running your own sketches, you may come across build errors or sketch crashes.

If the preprocessor (the first step in the build process) finds an error, then it will report it in the message area and jump to the offending line. These errors are generally syntax errors. These types of errors may be frustrating if you are a beginner, but you can find help by searching from the [main Processing website](https://processing.org/).

If the compiler (the next step) finds an error, it will report the error in the console and list some information about the error. The compiler errors may be difficult to read at first but they actually provide a lot of useful information for fixing problems. Note that the line numbers listed by the compiler do not correspond to line numbers in your sketch.

If your sketch crashes while running, then the error message and stack trace will appear in the message area and console, respectively.

For bugs in your app that do not cause crashes, you can try debugging using [`println()`](https://processing.org/reference/println_.html) statements. The output from your sketch will appear in the console.

If you encounter a build error that is not due to your faulty code, then please [report it as an issue](https://github.com/Calsign/APDE/issues). However, you should check to see if the issue has been reported already before creating a new issue; if it has then you can add a comment to the existing issue.

## Sketch Properties

You can open the Sketch Properties view from the menu to modify various meta-information about the sketch.

The first set of properties configure some common pieces of the AndroidManifest.xml file in the sketch folder. While you can edit the manifest directly, it is recommended not to as damaging it can break your sketch.

The sketch display name is the "pretty" sketch name that shows up in the Android launcher after you install the sketch.

The version code and version name are primarily used when releasing your app, such as on Google Play. The version code is an integer that represents the iteration of the sketch; you typically increase it by one with each release. The version name is the "pretty" version that is shown to the user.

In order to use certain device functionality, such as connecting to the internet, writing files on the external storage, using the camera, accessing bluetooth, and a host of other features, you must enable the corresponding permission from the Sketch Permissions screen. For more information, see the permissions reference on the [Android developers site](https://developer.android.com/guide/topics/permissions/requesting.html).

 > Tip: You can long-press a permission in the permissions screen to see what functionality it enables.

You may specify a locked orientation for the sketch, which will prevent the screen from rotating.

The second set of properties affects the sketch folder.

The "Show Sketch Folder" option is supposed to open the sketch folder in an external file manager, but unfortunately most file managers do not actually display the sketch folder properly.

You must add files to the data folder in order to use them in your sketch. For example, images, .csv files, and any other external data must be added to the data folder. Note that, for some reason, not all file managers properly provide APDE with the path to the file that you selected; as such you may have to use a different file manager or copy the path in directly.

"Change Sketch Icon" opens a dialog for changing the icon of your sketch as displayed in the Android launcher. You can select any image file to use as an icon (note that the same difficulties with file selection as with adding files to the data folder apply). You can then choose the crop mode and select "OK" to use the new icon.

 > Tip: The sketch icon is also used in the sketch manager drawer, which may help you organize your sketches.

### Tools

There are many tools available in the tools menu, accessed from the menu in the editor. Some of these tools are straightforward while others are described in their own Wiki pages. The tools will not be enumerated here but they contain a lot of important functionality and are thus worthy of exploration.

### Next Steps

Now that you have mastered the basics of APDE, you may wish to move onto some more advanced topics:

 - [Installing Contributed Libraries](https://github.com/Calsign/APDE/wiki/Installing-Contributed-Libraries)
 - [Exporting as a Signed Package](https://github.com/Calsign/APDE/wiki/Exporting-as-a-Signed-Package)

Additional documentation:

 - [Main page and FAQ](https://github.com/Calsign/APDE/wiki)
 - [Features Overview](https://github.com/Calsign/APDE/wiki/Features-Overview)
 - [Supported Devices](https://github.com/Calsign/APDE/wiki/Supported-Devices)
 - [Required Permissions (for APDE itself)](https://github.com/Calsign/APDE/wiki/Required-Permissions)

Technical documentation:

 - [Custom Build Chain](https://github.com/Calsign/APDE/wiki/Custom-Build-Chain-(Technical))