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

