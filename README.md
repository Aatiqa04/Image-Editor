# Image Editor

An Android image-editing application built with Kotlin and Jetpack Compose. It lets users pick an image from the gallery (or capture one with the camera) and apply a range of edits — filters, cropping, background and foreground changes, stickers, polygon selection, and more.

## Features

- **Basic editing** — adjust brightness, contrast, saturation, and other foundational properties.
- **Advanced editing** — fine-grained image manipulation tools.
- **Filters** — apply preset filters via the filter management screen.
- **Cropping & selection** — crop images and make rectangular or polygonal selections.
- **Change background / foreground** — replace or modify the background and foreground layers of an image.
- **Stickers & overlays** — add stickers and additional images on top of the canvas.
- **Polygon selection** — select arbitrary polygonal regions for targeted edits.

## Tech Stack

- **Language:** Kotlin
- **UI:** Jetpack Compose, Material 3
- **Image loading:** [Coil](https://coil-kt.github.io/coil/) and [Glide](https://github.com/bumptech/glide)
- **Cropping:** [Android-Image-Cropper](https://github.com/CanHub/Android-Image-Cropper) (CanHub)
- **Networking:** OkHttp, org.json
- **Architecture:** Single-module Android app using Compose `ComponentActivity` screens

## Project Structure

```
Image-Editor/
├── app/
│   ├── src/main/
│   │   ├── java/com/example/imageeditor/
│   │   │   ├── LandingScreen.kt           # Entry activity (LAUNCHER)
│   │   │   ├── Basic_Editing.kt
│   │   │   ├── Advance_Editing.kt
│   │   │   ├── FilterManagement.kt
│   │   │   ├── Change_Background.kt
│   │   │   ├── Change_Foreground.kt
│   │   │   ├── Selectiona_And_cropping.kt
│   │   │   ├── Polygon.kt
│   │   │   ├── SC_HomeScreen.kt
│   │   │   ├── SC_Middle_action.kt
│   │   │   ├── SC_polygoSelection.kt
│   │   │   ├── SC_stickerAndImage.kt
│   │   │   └── ui/theme/                  # Compose theme (Color, Theme, Type)
│   │   ├── res/
│   │   └── AndroidManifest.xml
│   └── build.gradle.kts
├── Documentation/
│   ├── SRS Document.pdf
│   ├── Component Diagram.pdf
│   └── Module Interface Specification.pdf
├── build.gradle.kts
└── settings.gradle.kts
```

## Requirements

- **Android Studio** Hedgehog or newer
- **JDK** 17 (Gradle Kotlin DSL build)
- **Android SDK** — `compileSdk = 34`, `minSdk = 24`, `targetSdk = 34`
- **Kotlin Compose Compiler** 1.5.1

## Getting Started

1. Clone the repository:
   ```bash
   git clone <repo-url>
   cd Image-Editor
   ```
2. Open the project in Android Studio and let Gradle sync.
3. Connect a device or start an emulator (API 24+).
4. Run the `app` configuration. The launcher activity is `LandingScreen`.

### Building from the command line

```bash
./gradlew assembleDebug          # build a debug APK
./gradlew installDebug           # install on a connected device
```

On Windows use `gradlew.bat` instead of `./gradlew`.

## Permissions

Declared in `AndroidManifest.xml`:

- `READ_EXTERNAL_STORAGE` — load images from the gallery
- `WRITE_EXTERNAL_STORAGE` — save edited images
- `INTERNET` — network requests

A `FileProvider` is configured under the authority `${applicationId}.provider` for sharing edited image files.

## Documentation

Additional design documents are available under the `Documentation/` directory:

- **SRS Document** — software requirements specification
- **Component Diagram** — high-level component architecture
- **Module Interface Specification** — module-level interface contracts

## License

This project is provided for educational purposes. Add a license file (e.g., MIT, Apache 2.0) before distributing.
