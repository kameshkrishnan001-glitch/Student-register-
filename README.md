# Home Tuition Academy – Attendance Manager (Android)

A standalone Android app. It works fully offline: no internet, no account with any company.
All data (students, attendance, fees, accounts) is stored on the phone.

The whole app is one web page: `app/src/main/assets/index.html`, shown inside a WebView.

## Get the .apk (GitHub, nothing to install)
1. Create a free account at github.com and a **new PRIVATE repository**.
2. Upload this one folder, **HomeTuitionAcademy**: open the repository, choose **Add file > Upload files**, and drag the whole folder in. Commit.
3. Open the **Actions** tab > **set up a workflow yourself**. Delete the sample text, paste the full contents of `build-apk.yml.txt` (inside the folder), and press **Commit changes**.
4. Go to **Actions > Build APK > Run workflow**. Wait about 3 minutes.
5. Open the finished run, download **HomeTuitionAcademy-apk**, unzip it to get `app-release.apk`.
6. Copy it to the phone and tap it. Allow "Install unknown apps" when asked.

## Or build with Android Studio
Open this folder in Android Studio, let it sync, then **Build > Build Bundle(s)/APK(s) > Build APK(s)**.
(Use the `release` variant for the same signing key; `debug` also works for testing.)

## First use
* The first screen asks you to create the **administrator** account. Then a **recovery code** is shown once.
  Write it down: it is the only way to reset a forgotten administrator password.
* The administrator can add teacher accounts in **Settings > Users** and reset their passwords.
* Teachers can mark attendance and view students; they cannot see fees, edit students, restore backups or manage users.
* Excel, PDF and backup files are saved to **Downloads/HomeTuitionAcademy** on the phone.
* WhatsApp buttons open the WhatsApp app with the message ready.

## Important
* **Back up regularly** (Settings > Download backup). Uninstalling the app or clearing its storage deletes all data.
* The data lives on one phone. There is no sync between phones.
* Sign-in protects the app screens, not the phone's storage. Use a phone screen lock as well.
* Signing key: `app/hta-release.keystore` (password in `app/build.gradle`) keeps updates installable over older versions.
  Keep the repository private. For Google Play, create your own key and change the `signingConfigs` block.
* Requires Android 10 or newer.
