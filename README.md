# Fretwork

Free guitar learning app for Android: a step-by-step Learn course, a microphone-scored Practice mode,
a Tuner and a library of 120 chords. Everything runs on the phone, no account and no internet needed.

## Get the APK from GitHub (about 10 minutes, no Android Studio needed)

1. Create a new empty repository on github.com (for example `fretwork`).
2. Upload this whole folder to it. From a terminal inside this folder:

   ```bash
   git init -b main
   git add .
   git commit -m "Fretwork"
   git remote add origin https://github.com/YOUR-NAME/fretwork.git
   git push -u origin main
   ```

3. Open the repository's **Actions** tab. The "Build Android APK" workflow starts by itself and takes
   about 5 to 10 minutes. (You can also start it with **Run workflow**.)
4. When it finishes, open the repository's **Releases** page and download **Fretwork.apk**.
5. On your Android phone, open that Releases page in Chrome, tap **Fretwork.apk**, and install it.
   Android will ask you to allow "Install unknown apps" for your browser the first time.
6. Open Fretwork and allow the microphone when asked. The app needs it to hear your guitar.

Every time you push a change, the workflow builds a fresh APK and replaces the one in Releases.

## Changing the app

The whole app is one file: `www/index.html`. Edit it, commit and push, and a new APK is built.

## Notes

- The APK is signed with Android's standard debug key, which is fine for installing on your own phone.
  Publishing on Google Play needs a release key and a bundle (`./gradlew bundleRelease`).
- To build on your computer instead: install Node 22, JDK 21 and Android Studio, then run
  `npm ci`, `npx cap sync android`, and `cd android && ./gradlew assembleDebug`.
  The APK appears in `android/app/build/outputs/apk/debug/`.
- Built with Capacitor. App id: `com.fretwork.app`.
