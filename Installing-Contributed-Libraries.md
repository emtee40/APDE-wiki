Follow these instructions to install a contributed library in APDE.

## Using the Installer

### Installation Steps
1. Download the properly-formatted library ZIP file as described below.
2. In APDE, navigate to (action overflow) > Tools > Import Library > Manage Libraries > (action overflow) > Install Compressed Library. Select the downloaded library with your favorite file manager.
3. Wait for the extraction and dexing process to complete. The dexing in particular may take a long time, but this is time that you don't have to waste every time that you build a sketch using the library.
4. The dialog will close and the library should appear in the list. It will now be automatically added to any sketch with the import statements at the top. To view the library's examples, open the sketch navigation drawer and navigate to the library's folder within "Library Examples".

### Properly Formatted Library
APDE's library installer is designed to install the zipped file that would be retrieved by the library manager on the desktop. It is currently capable of installing libraries formatted as per the Processing [library folder structure specifications](https://github.com/processing/processing/wiki/Library-Guidelines#folder-structure). All libraries that are available from the library manager conform to this structure.

For an example of a properly formatted library, see [Ketai](https://code.google.com/p/ketai/downloads/detail?name=Ketai_v9.zip&can=2&q=). This file, after being downloaded, is directly consumable by APDE's installer.

APDE's library installer takes care of extracting the folder structure and dexing the library for you.
## Manual Installation
If you are developing a library, you have a library that is not properly formatted, or you encounter issues with the library installer, then you can still install the library manually.

### Installation Steps
1. If the library is in a ZIP or other type of compressed file, then extract it.
2. Copy the extracted folder to the libraries folder in the Sketchbook folder and rename it to the desired name of the library., e.g. "path/to/Sketchbook/libraries/Ketai/".
3. Ensure that the library JAR file is located in the "library" folder in the library's folder with the same name as the enclosing folder, e.g. "Ketai/library/Ketai.jar". Copy any additional JAR files to this folder.
4. Optionally, ensure that the library's examples are located in the "examples" folder in the library's folder, e.g. "Ketai/examples".
5. Optionally, ensure that the "library.properties" file is located at the root of the library's folder, e.g. "Ketai/library.properties".
6. Create a new folder at the same level as the "library" folder with the name "library-dex", e.g. "Ketai/library-dex/".
7. Open APDE and navigate to (action overflow) > Tools > Import Library > Manage Libraries > (action overflow) > DX Dexer. Note: The library should already appear in the list, but it has not been fully installed yet.
8. In the "Input File" text box, enter the path to the library JAR file, e.g. "path/to/Sketchbook/libraries/Ketai/library/Ketai.jar". You may use the file select button to aid in locating this file.
9. In the "Output File" text box, enter the same path as above, but change the "library" folder to "library-dex" and change the library JAR file to "_libraryName_-dex.jar", e.g. "path/to/Sketchbook/libraries/Ketai/library-dex/Ketai-dex.jar".
10. Press the "Dex" button. Wait for the dexing process to complete.
11. Repeat steps 7 through 10 for any additional library JAR files.
12. When the dialog closes, the library has been fully installed. It will now be automatically added to any sketch with the import statements at the top.