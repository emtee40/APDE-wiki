You can install Processing libraries with APDE, see [installing contributed libraries](https://github.com/Calsign/APDE/wiki/Installing-Contributed-Libraries). But if you want to use a library that is just distributed as a `.jar`, you can still use it without packaging it into a Processing library. Follow these steps:

1. Using an external file manager, create a directory named `libs` in the sketch folder.
2. Copy the `.jar` into `libs`. We will assume it is named `some-lib.jar`, but you can adjust the following steps based on the name of your library.
3. Create a `libs-dex` folder in the sketch folder, next to `libs`.
4. In APDE, open the library manager and select the "DX Dexter" tool from the menu.
5. Enter the full path to `some-lib.jar` in the "Input File" field.
6. In "Output File", put the full path to `<sketch folder>/libs-dex/some-lib-dex.jar`.
7. Select "Dex" to convert the library to dex format.
8. Use your library like normal.

Notes:
* You must add the library to each sketch that needs it, this is not global.
* Libraries must be converted to dex so they they can be used on Android. For contributed libraries the conversion is automatic, but automatic conversion for jar libraries is not currently supported.
* The original jar is still needed by the compiler, so you need both.