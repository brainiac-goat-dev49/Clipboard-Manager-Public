# Clipboard Manager for Android

An intelligent, modern, and privacy-focused Android clipboard and screenshot management utility built with **Kotlin**, **Jetpack Compose**, and **Material Design 3**.

---

## ✨ Features

- 📋 **Seamless Clipboard Monitoring**
  - Automatically captures copied text, snippets, URLs, and formatted content in real time.
  - Runs efficiently via an Android Accessibility Service without background battery drain.

- 📸 **Automatic Screenshot Ingestion**
  - Monitors and captures newly taken screenshots directly into your clipboard history.
  - Quick-copy and share images instantly without opening your gallery.

- 🫧 **Floating Desktop Overlay Bubble**
  - Draggable, floating bubble that sits over any app.
  - Tap to expand your clipboard history, quickly paste recent snippets, or hide individual items on the fly.
  - Pause or dismiss anytime directly from the bubble menu.

- 🌐 **18-Language Multilingual Support**
  - Comprehensive native translations for:
    - ��🇸 English (`en_US`)
    - 🇪🇸 Spanish (`es_ES`)
    - 🇫🇷 French (`fr_FR`)
    - 🇩🇪 German (`de_DE`)
    - 🇮🇹 Italian (`it_IT`)
    - 🇵🇹 Portuguese (`pt_PT`)
    - 🇷🇺 Russian (`ru_RU`)
    - 🇨🇳 Simplified Chinese (`zh_CN`)
    - 🇯🇵 Japanese (`ja_JP`)
    - 🇰🇷 Korean (`ko_KR`)
    - 🇳🇱 Dutch (`nl_NL`)
    - 🇸🇪 Swedish (`sv_SE`)
    - 🇵🇱 Polish (`pl_PL`)
    - 🇹🇭 Thai (`th_TH`)
    - 🇹🇷 Turkish (`tr_TR`)
    - 🇻🇳 Vietnamese (`vi_VN`)
    - 🇮🇩 Indonesian (`id_ID`)
    - 🇸🇦 Arabic (`ar_AR`) *(with full dynamic Right-to-Left (RTL) layout support)*

- 📂 **Smart Folders & Instant Search**
  - Automatically organizes items into **Texts**, **Links**, **Screenshots**, and **Synced** categories.
  - Real-time search across your entire clipboard history.

- ☁️ **Cloud Synchronization & Backup**
  - Optional secure cloud account synchronization to back up and restore your clips across devices.

- 🛡️ **Privacy-First & Offline Storage**
  - Local database storage powered by Android Room / SQLite.
  - One-tap history wipe to securely erase all cached clips and screenshots.

---

## 🛠️ Tech Stack & Architecture

- **Language:** Kotlin 2.0+
- **UI Toolkit:** Jetpack Compose with Material 3 (M3) dynamic color theming
- **Architecture:** Clean MVVM with Kotlin Coroutines & `StateFlow`
- **Database:** Android Room with SQLite
- **Image Loading:** Coil Compose
- **System Integrations:**
  - `AccessibilityService` for system-wide clipboard interception
  - `WindowManager` for interactive floating overlay bubble
  - `MediaStore` observer for screenshot detection
- **Compatibility:** Android 5.0 (API level 21) through Android 15+ (API level 35)

---

## 📂 Project Structure

```
app/src/main/java/com/example/
├── MainActivity.kt                  # Main entry point, dashboard UI & tab navigation
├── data/
│   ├── ClipboardDatabase.kt         # Room database definition & migrations
│   ├── ClipboardItem.kt             # Data models & entity definitions
│   ├── ClipboardDao.kt              # Room data access objects & reactive queries
│   ├── ClipboardRepository.kt       # Repository layer with deduplication logic
│   └── sync/
│       └── AuthAndSyncManager.kt    # Account auth & cloud sync controller
├── localization/
│   ├── AppLanguage.kt               # Language models, flags & RTL definitions
│   ├── AppStrings.kt                # 18-Language translation strings
│   └── LanguageManager.kt           # Reactive language state manager & preferences
├── service/
│   └── ClipboardAccessibilityService.kt # Background accessibility monitor & overlay bubble
└── ui/
    ├── screens/
    │   ├── LoadingSplashScreen.kt   # Animated brand splash loader
    │   └── LanguageSelectionScreen.kt # Interactive language picker
    └── theme/
        ├── Color.kt                 # Material 3 color palettes
        ├── Theme.kt                 # App theme provider & dynamic color support
        └── Type.kt                  # Typography definitions
```

---

## 🚀 Building & Installing

### Prerequisites
- Android Studio Ladybug (2024.2+) or newer
- JDK 17+
- Android SDK with API level 35

### Command Line Build
```bash
# Clone the repository
git clone https://github.com/brainiac-goat-dev49/Clipboard-Manager.git
cd Clipboard-Manager

# Assemble debug APK
./gradlew assembleDebug
```
The generated APK will be available at:
`app/build/outputs/apk/debug/app-debug.apk`

---

## 🔐 Required Permissions

- **Accessibility Service:** Used solely to detect clipboard updates across running applications.
- **Display over other apps (`SYSTEM_ALERT_WINDOW`):** Required to display the floating overlay bubble.
- **Photos / Media Access (`READ_MEDIA_IMAGES` / `READ_EXTERNAL_STORAGE`):** Used to capture and ingest new screenshots into your clipboard library.

---

## ℹ️ Source Code

The complete source code for this project is maintained in a private repository. For inquiries about the source code, features, or contributions, please reach out directly.

---

## 📄 License

This project is licensed under the Apache License 2.0. See [LICENSE](LICENSE) for details.