# Kutira Kone App

A modern Android application built with **Kotlin** and **Java**, featuring Jetpack Compose for the UI.

## Features

- 🎨 Modern Material3 Design
- 📱 Jetpack Compose UI Framework
- 🔧 Kotlin + Java Support
- ✅ Unit and Instrumented Tests
- 🏗️ MVVM-ready Architecture

## Project Structure

```
kutira-kone-app/
├── app/
│   ├── src/
│   │   ├── main/
│   │   │   ├── kotlin/com/example/kutirakoneapp/
│   │   │   │   ├── MainActivity.kt
│   │   │   │   └── ui/theme/
│   │   │   │       ├── Theme.kt
│   │   │   │       ├── Color.kt
│   │   │   │       └── Type.kt
│   │   │   ├── res/
│   │   │   │   ├── values/
│   │   │   │   ├── strings.xml
│   │   │   │   ├── colors.xml
│   │   │   │   └── themes.xml
│   │   │   └── AndroidManifest.xml
│   │   ├── test/
│   │   └── androidTest/
│   └── build.gradle.kts
├── build.gradle.kts
├── settings.gradle.kts
└── .gitignore
```

## Requirements

- Android SDK 34 (API Level 34)
- Minimum SDK: 24 (API Level 24)
- Java 1.8+
- Gradle 8.5+

## Building the Project

### Build Debug APK
```bash
./gradlew assembleDebug
```

### Build Release APK
```bash
./gradlew assembleRelease
```

### Run Tests
```bash
./gradlew test                    # Unit tests
./gradlew connectedAndroidTest    # Instrumented tests
```

### Build and Install on Device
```bash
./gradlew installDebug
```

## Dependencies

- **Android Core**: androidx.core, androidx.appcompat
- **Jetpack Compose**: UI, Material3, Preview
- **Material Design**: Material3 components
- **Testing**: JUnit, Espresso, Compose UI testing

## Development

### Setting Up IDE

**Android Studio:**
1. Open the project in Android Studio
2. Sync Gradle files
3. Connect an Android device or start an emulator
4. Run the app

**VS Code with Flutter/Dart Extensions:**
1. Install Android development tools
2. Run `flutter pub get` (if using Flutter)
3. Use Android emulator or physical device

## Contributing

Feel free to contribute by:
1. Forking the repository
2. Creating a feature branch
3. Submitting pull requests

## License

This project is open source and available under the MIT License.

## Contact

For questions or suggestions, please open an issue on GitHub.
