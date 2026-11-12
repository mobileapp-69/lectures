# Getting Started with Flutter for Android (macOS)

This guide covers setting up Flutter for Android development on macOS.
**Android Studio is required** for this class because it provides the Android
SDK tools and emulator management.

## 1. Install Flutter and an editor

1. Install [Visual Studio Code](https://code.visualstudio.com/).
2. Install the Dart and Flutter extensions.
3. Install the Flutter SDK using the
   [manual installation guide](https://docs.flutter.dev/install/manual).

## 2. Install Android Studio and SDK components

1. Install [Android Studio](https://developer.android.com/studio).
2. Open Android Studio's **SDK Manager**.
3. In the **SDK Platforms** tab, install Android 16 (API 36) or the platform
   version specified for the class.
4. In the **SDK Tools** tab, install or verify these components:
   - Android SDK Build-Tools
   - Android SDK Command-line Tools
   - Android Emulator
   - Android SDK Platform-Tools
   - CMake
   - NDK (Side by side)

Use the versions specified by the class project, if any. Otherwise, use the
versions recommended by Android Studio and Flutter; do not assume that a
specific NDK or CMake version is required for every project. See the
[Flutter Android setup guide](https://docs.flutter.dev/platform-integration/android/setup)
for details.

## 3. Set up an Android emulator

1. Open Android Studio's Device Manager and create a virtual device (for
   example, a Pixel phone).
2. Select an Android system image and finish creating the device.
3. Start the emulator.
4. Run `flutter emulators` to list available emulators and `flutter devices` to
   check that the running emulator is recognized.

## 4. Connect a physical Android device (optional)

1. Turn on Developer Options and USB debugging on your Android device.
2. Connect it to your Mac with USB and authorize the computer if prompted.
3. Run `flutter devices` to check that Flutter recognizes it.

## 5. Add Flutter and Android tools to your PATH

Add the Flutter SDK's `bin` directory to your shell's `PATH`. For example, if
you installed Flutter in `~/develop/flutter`, add this line to `~/.zprofile`:

```sh
export PATH="$HOME/develop/flutter/bin:$PATH"
```

Replace the example path with your Flutter SDK location, then reopen your
terminal. Android Studio's default Android SDK location is usually
`~/Library/Android/sdk`. Add its `platform-tools` directory to `PATH` if you
want to run `adb` from a terminal:

```sh
export PATH="$HOME/Library/Android/sdk/platform-tools:$PATH"
```

## 6. Verify the setup and run an app

1. Run `flutter doctor` and address any issues reported for Flutter and the
   Android toolchain.
2. Run `flutter doctor --android-licenses` and review and accept the Android
   SDK licenses.
3. Create a Flutter project, start an emulator or connect a device, then run
   the app with `flutter run`.
