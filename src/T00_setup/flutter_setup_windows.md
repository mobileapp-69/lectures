# Getting Started with Flutter (Windows)

This setup compiled successfully on my Windows machine with Flutter 3.47.9.
The versions below are what I had installed as of 2026-11-12; they are not
necessarily required for every project or the latest available versions.

## 1. Install Flutter and an editor

1. Install [Visual Studio Code](https://code.visualstudio.com/).
2. Install the Dart and Flutter extensions.
3. Install the Flutter SDK using the [manual installation guide](https://docs.flutter.dev/install/manual).

## 2. Install Android Studio and SDK components

Install [Android Studio](https://developer.android.com/studio), then follow the
[Flutter Android setup guide](https://docs.flutter.dev/platform-integration/android/setup)
to install the additional Android SDK components.

In Android Studio's SDK Manager, install Android 16 ("Baklava") from the **SDK
Platforms** tab. I have Android SDK Platform 36.1 installed.

In the **SDK Tools** tab, I have:

- Android SDK Build-Tools 36.0.0
- NDK (Side by side) 28.2.13676358
- Android SDK Command-line Tools
- CMake 4.1.12
- Android Emulator
- Android SDK Platform-Tools

These are the versions used for my successful build. Use a project-pinned
version if one is specified.

## 3. Set up an Android emulator

1. Open Device Manager and create a virtual device (for example, Pixel 6).
2. Select a system image (for example, Android 16 "Baklava").
3. Finish the setup and start the emulator.
4. Run `flutter emulators` to list available emulators, and `flutter devices` to
   check connected devices.

## 4. Configure Windows environment variables

- Add the Flutter SDK's `bin` folder to your system `PATH`, if you have not
  already.
- Set `ANDROID_HOME` to your Android SDK location (usually
  `%LOCALAPPDATA%\Android\Sdk`).
- If setting `JAVA_HOME`, use the actual location of your JDK. Android Studio's
  bundled JDK is usually under
  `%ProgramFiles%\Android\Android Studio\jbr`.
- Add these Android SDK folders to `PATH`:
  - `%LOCALAPPDATA%\Android\Sdk\platform-tools`
  - `%LOCALAPPDATA%\Android\Sdk\build-tools\36.0.0` (or the version you installed)

After configuring `PATH`, you should be able to run:

- `apksigner --version`
- `adb --version`
- `& "$env:ProgramFiles\Android\Android Studio\jbr\bin\keytool.exe" --version`

I run `keytool` by its full path to avoid conflicts with other Java
installations.

## 5. Connect a physical Android device (optional)

1. Turn on Developer Options and USB Debugging on your device.
2. Connect the device via USB and authorize the computer if prompted.
3. Run `flutter devices` to check that Flutter recognizes it.

## 6. Verify the setup and run an app

1. Run `flutter doctor` to check for missing dependencies.
2. Create a Flutter project.
3. Run the app with `flutter run`.
