# System Setup Guide

This guide explains how to set up the Smart Crop Monitoring system for both development and runtime use.

## 1) Development Setup (Flutter)

### Prerequisites
- Git
- Flutter SDK (includes Dart)
- Android Studio (for Android SDK and emulator)
- Xcode (macOS only, for iOS builds)
- A physical device or emulator/simulator

### Install Flutter
1. Download Flutter: https://docs.flutter.dev/get-started/install
2. Add Flutter to PATH.
3. Run:
   ```bash
   flutter doctor
   ```
4. Follow the doctor suggestions to install missing dependencies.

### Android Setup
1. Install Android Studio.
2. Open Android Studio > SDK Manager and install:
   - Android SDK Platform
   - Android SDK Build-Tools
   - Android SDK Command-line Tools
3. Accept licenses:
   ```bash
   flutter doctor --android-licenses
   ```

### iOS Setup (macOS only)
1. Install Xcode from the App Store.
2. Run:
   ```bash
   sudo xcode-select --switch /Applications/Xcode.app/Contents/Developer
   sudo xcodebuild -runFirstLaunch
   ```

### Web Setup
1. Enable web support:
   ```bash
   flutter config --enable-web
   ```

### Windows/Desktop Setup (optional)
1. Enable desktop support:
   ```bash
   flutter config --enable-windows-desktop
   ```

### Get Dependencies
From the project root:
```bash
flutter pub get
```

### Run the App (Dev)
```bash
flutter run
```

## 2) Runtime Setup (End User)

### Android
- Build a release APK or AAB:
  ```bash
  flutter build apk
  # or
  flutter build appbundle
  ```
- Install the APK on a device.

### iOS
- Build with Xcode and distribute via TestFlight or App Store.

### Web
- Build:
  ```bash
  flutter build web
  ```
- Host the `build/web` folder on a web server.

### Windows
- Build:
  ```bash
  flutter build windows
  ```
- Distribute the generated binary in `build/windows/runner/Release`.

## 3) Project Notes
- Configuration files are in `android/`, `ios/`, `web/`, and `windows/`.
- Assets live under `Assets/` and are registered in `pubspec.yaml`.
- If the app uses external services (e.g., Firebase, APIs), add their keys to the appropriate config files and keep them out of source control.

## 4) Troubleshooting
- Re-run:
  ```bash
  flutter doctor
  ```
- Clean and rebuild:
  ```bash
  flutter clean
  flutter pub get
  ```
