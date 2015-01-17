Follow these instructions to export a signed package through APDE's export tool.

Disclaimer: I (CalsignLabs, William Smith) am not a security expert. I have written this guide simply to make it easier for users to utilize the export functionality provided by APDE.

## Background

### Why should I export my sketch?

You should consider exporting your sketch whenever you wish to share or distribute it. It is not practical to do this every time that you run the sketch for development because it takes too much time every iteration. However, exporting does have many advantages for the finalized, or simply the preview version, of a sketch that you intend to be consumable by another device.

First and foremost, if you want to upload your sketch to Google Play (or any other app distribution service), then you must sign your APK file for release. Sketches that are not signed (debug builds) are marked as such and may present security vulnerabilities. For this reason, most major app stores require that sketches be signed. This is a level of professionalism that is expected of any serious plan to distribute your sketch to end-users.

Even if you don't intend to publish your sketch and merely want to share it with a couple of friends, then signing your sketch would still be a good idea.

### Keys, keystores, certificates, and passwords

In order to export your sketch, you must sign it with a key/certificate combo. A debug build is signed with an auto-generated debug key/certificate that is not suitable for release builds. The only difference between a debug build and a release build is the key/certificate used.

Keys/certificates contain information about the signer (the certificate) and an alias with a password (the key). Technically, the key is another piece of information that is part of the certificate. Once you have created a key/certificate, you cannot edit it (at least without the help of advanced tools, to my knowledge).

Keys/certificates live in the keystore (spelled "key store" by some sources), which is a collection of key/certificate combos and their storage in memory. A keystore may contain multiple keys/certificates. A keystore is protected with a password. Additionally, each key is protected by a password. A key may use the same password as the keystore and, in most cases, this does not present a security issue.

For most usage cases, you will only need to create one keystore with one key/certificate to sign all of your sketches. There are advantages to using different keys with different sketches, but there are also advantages to using the same key. Neither of these advantages will likely apply to you unless you work for several businesses or are able make extensive use of native Android APIs.

When creating a keystore, make sure that you store it in a safe location. If a hacker has access to your keystore, then they can potentially impersonate you through your keys.

When creating passwords for both keystores and keys, make sure that they are sufficiently secure. APDE does not provide password strength analysis, and only recommends a minimum character count of eight characters. A strong password would be twenty randomly generated characters. However, password security may get in the way of ease of use if you are a hobbyist. In the end, the solution is entirely up to you.

## Exporting the Sketch

### Export Steps

1. In APDE, navigate to (action overflow) > Tools > Export Signed Package.
2. If you have already created a keystore or wish to use an existing keystore, then enter (or select with the folder button) the path to the keystore, enter the password, and skip to step 7.
3. Select the "+" button in the top right corner to enter the keystore creation dialog.
4. Enter (or select with the folder button) the path to the new keystore. Note: This file should not already exist. The file extension should be ".bks" for a BouncyCastle (BKS) keystore or ".jks", ".ks", ".keystore", or any other extension for a Java (JKS) keystore.
5. Enter the keystore password. Enter it again in the confirmation field.
6. Select "Create" to create the keystore at the specified location.
7. If the keystore already contains a key/certificate and you do not want to create a new key/certificate, then select the key alias, enter the password, and skip to step 14.
8. Select the "+" button to the right of the key alias field to create a new key/certificate.
9. Enter the alias for the key. This is the required name that is publicly visible.
10. Enter the key password. Enter it again in the confirmation field.
11. Enter the key validity period. The key/certificate will remain usable for this many years after the key/certificate has been created. Sketches that are signed with this key will remain usable after this time period expires, but you will not be able to sign any more sketches with it. Twenty-five years is recommended.
12. Optionally, enter the certificate information in the designated fields. If any information is not provided, its field will be automatically filled with "None". This information is publicly accessible.
13. Select "Create" to create the key/certificate.
14. Review the information about the selected key/certificate. The certificate information is available from the "i" button to the right of the key alias field. When you are ready, select "Export" to export the sketch to "bin/_sketchName_.apk" within the sketch folder.