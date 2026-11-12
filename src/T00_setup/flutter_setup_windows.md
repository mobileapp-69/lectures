# Getting Started with Flutter (Windows)

- Install VSCode
  - Install Dart and Flutter extensions
- Install Flutter SDK
  - [Manual Installation](https://docs.flutter.dev/install/manual)

- Install [Android Studio](https://developer.android.com/studio)
  - [Setup](https://docs.flutter.dev/platform-integration/android/setup) additional Android SDK components.

SDK Platform Tab

- Adndroid 16.0 ("Baklava")
  - Android SDK Platform 36.1
    SDK Tools Tab
- Android SDK 36.0.0
- NDK (Side by Side) 28.2.13676358. (Updated 2026-11-12, you need this version specifically, not newer)
- Android SDK Command-line Tools (latest)
- Cmake 4.1.12 (latest)
- Android Emulator
- Android SDK Platform-Tools

- Setup Virtual Device in the device manager
  - Create a new virtual device (e.g. Pixel 6)
  - Select a system image (e.g. Android 16.0 "Baklava")
  - Finish the setup and start the emulator.

- Try running emulator. Verify with `flutter emulators` command.

- Setup path environment variable
  - Add the Flutter SDK path to your system's PATH environment variable. (If you have not done so already)
  - Add ANDROID_HOME=%AppData%\Local\Android\Sdk environment variable to point to your Android SDK location.
  - Add JAVA_HOME=%ProgramFiles%\Android\Android Studio\jbr environment variable to point to your Java JDK location.
  - Update path
    - %LOCALAPPDATA%\Android\Sdk\platform-tools
    - %LOCALAPPDATA%\Android\Sdk\build-tools\36.0.0 (or the version you installed)

You should be able to run these tools

- apksigner --version
- adb --version
- & "$env:ProgramFiles\Android\Android Studio\jbr\bin\keytool.exe" --version (I am not adding this to the path becuase it might conflict with existing Java installations)

- Set up a physical device
  - Turn on Developer Options and USB Debugging on your Android device.
  - Connect your device via USB.
  - Try running `flutter devices` to see if your device is recognized.

- Verify your installation
  - Run `flutter doctor` in your terminal to check for any missing dependencies.
- Create a new Flutter project
- Run the app using `flutter run`

---
