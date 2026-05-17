# DeccanDigest APK — Complete Build Guide

## What's Inside This Package

```
deccandigest_app/
├── lib/
│   ├── main.dart                    ← App entry point
│   ├── theme/app_theme.dart         ← Colors, dark theme
│   ├── data/social_links.dart       ← All URLs (Facebook, Instagram, etc.)
│   ├── services/launcher_service.dart
│   ├── screens/
│   │   ├── splash_screen.dart       ← Welcome screen with video + sponsors
│   │   ├── home_screen.dart         ← 8 buttons + ad banners
│   │   ├── contact_screen.dart      ← Email / WhatsApp / Website
│   │   └── exit_screen.dart         ← Exit video + app close
│   └── widgets/
│       ├── dash_button.dart         ← Grid button component
│       ├── ad_banner.dart           ← Auto-rotating ad banners
│       └── social_list_sheet.dart   ← Facebook / Instagram list popup
├── assets/
│   ├── logo/dd_logo.png
│   ├── sponsors/gmr.png, corefit.png
│   ├── banners/banner_gmr.png, banner_kashmir.png, banner_muchaley.png
│   └── intro/intro.mp4
├── pubspec.yaml
└── android/app/src/main/AndroidManifest.xml
```

---

## Step 1 — Install Flutter

### Windows
1. Download Flutter SDK: https://docs.flutter.dev/get-started/install/windows
2. Extract to `C:\flutter`
3. Add `C:\flutter\bin` to your PATH environment variable
4. Run in Command Prompt:
   ```
   flutter doctor
   ```

### macOS
```bash
brew install --cask flutter
flutter doctor
```

---

## Step 2 — Install Android Studio

1. Download from: https://developer.android.com/studio
2. During setup, install:
   - Android SDK
   - Android SDK Platform-Tools
   - Android Emulator (optional)
3. Open Android Studio → More Actions → SDK Manager
4. Install **Android API 34** (or latest)

---

## Step 3 — Accept Licenses

Run this once in terminal:
```bash
flutter doctor --android-licenses
# Press 'y' and Enter for each prompt
```

---

## Step 4 — Copy This Project

1. Copy the entire `deccandigest_app/` folder to your computer
2. Open terminal inside that folder:
   ```bash
   cd deccandigest_app
   ```

---

## Step 5 — Get Dependencies

```bash
flutter pub get
```

You should see: `Got dependencies!`

---

## Step 6 — Build the APK

### Debug APK (for testing — quick)
```bash
flutter build apk --debug
```

### Release APK (for sharing / Play Store)
```bash
flutter build apk --release
```

### APK Location after build:
```
build/app/outputs/flutter-apk/app-release.apk
```

Send this file to your Android phone — tap to install.

---

## Step 7 — Install on Phone

1. On your Android phone:
   - Go to **Settings → Security → Unknown Sources** → Enable
   - (On Android 8+: Settings → Apps → Special app access → Install unknown apps)

2. Transfer `app-release.apk` to your phone via:
   - WhatsApp (send to yourself)
   - USB cable
   - Google Drive

3. Tap the APK file → Install

---

## To Update Social Links Later

Edit this one file:
```
lib/data/social_links.dart
```

Change any URL, save, rebuild.

---

## To Replace Ad Banners

Replace these image files (keep same filenames):
```
assets/banners/banner_gmr.png
assets/banners/banner_kashmir.png
assets/banners/banner_muchaley.png
```
Then rebuild.

---

## To Change App Icon

1. Replace `assets/icons/app_icon.png` with your icon (1024×1024 PNG)
2. Add this package to pubspec.yaml:
   ```yaml
   dev_dependencies:
     flutter_launcher_icons: ^0.13.1
   ```
3. Add to pubspec.yaml:
   ```yaml
   flutter_icons:
     android: true
     ios: false
     image_path: "assets/icons/app_icon.png"
   ```
4. Run:
   ```bash
   flutter pub get
   flutter pub run flutter_launcher_icons
   flutter build apk --release
   ```

---

## Troubleshooting

| Error | Fix |
|-------|-----|
| `flutter: command not found` | Add Flutter to PATH |
| `Android license not accepted` | Run `flutter doctor --android-licenses` |
| `Gradle build failed` | Run `flutter clean` then `flutter build apk` |
| `SDK not found` | Open Android Studio → SDK Manager → install API 33/34 |
| Video not playing | Check `assets/intro/intro.mp4` exists and pubspec.yaml lists assets folder |

---

## App Features Summary

| Feature | Status |
|---------|--------|
| Splash screen with video | ✅ |
| Logo animation | ✅ |
| Powered by + sponsor logos | ✅ |
| 8 dashboard buttons | ✅ |
| Facebook pages list (16 pages) | ✅ |
| Instagram profiles list (8) | ✅ |
| WhatsApp Channel link | ✅ |
| Telegram Channel link | ✅ |
| X / Twitter link | ✅ |
| YouTube link | ✅ |
| Website link | ✅ |
| Contact Us screen | ✅ |
| Auto-rotating ad banners | ✅ |
| Exit screen with video | ✅ |
| Dark theme | ✅ |
| Portrait lock | ✅ |

---

*Built for DeccanDigest — The Largest News Network of Deccan Region*
