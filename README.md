# 🖼️ Store Asset Studio

Generate every platform's app icons and store assets from a single source image - Microsoft Store, Windows `.ico`, macOS, Android, iOS, Chrome Extension, Favicon, Social/OG and Flatpak. Also resizes your screenshots to the sizes the Apple App Store and Microsoft Store accept.

A desktop app for **Windows** and **macOS**. Everything runs locally on your device - your image is never uploaded.

---

## What it does

Drop in one icon image. Pick your target platforms. Save a ZIP with every asset pre-sized, named, and organized into folders, ready to drop straight into your project.

| Platform | Assets included |
|---|---|
| 🪟 Microsoft Store | 43 assets - badge logos, tiles, splash screen, store listing screenshots, a multi-resolution Windows `.ico` and a 1024px PNG |
| 🤖 Android (Play Store) | 8 assets - mipmap densities + feature graphic, plus adaptive-icon foreground/background files |
| 🍎 iOS (App Store) | 16 assets - iPhone & iPad icon sizes |
| 🍏 macOS | 7 assets - app icon sizes 16 to 1024px |
| 🌐 Chrome Extension | 7 assets - extension icons + Web Store promo tiles |
| 🌐 Favicon (browser tab) | 6 assets - standard favicon sizes + Apple touch icon |
| 🔗 Social / OG image | 5 assets - Open Graph, Twitter Card, LinkedIn, Facebook cover, YouTube thumbnail |
| 📦 Flatpak (Flathub) | 4 assets - app icons at 64, 128, 256, 512px |

The ZIP contains folders like:

```
visual-assets.zip
├── Assets/                       ← Microsoft Store visual assets
│   ├── BadgeLogo.png
│   ├── Square150x150Logo.png
│   ├── Square44x44Logo.png
│   ├── Wide310x150Logo.png
│   ├── SplashScreen.png
│   └── ...
├── Screenshots/                  ← Microsoft Store listing images
│   ├── Poster 9x16.png
│   ├── Box 1x1.png
│   └── ...
├── Windows/
│   ├── app_icon.ico              ← multi-resolution desktop icon
│   └── app_icon.png              ← 1024x1024
├── macOS/
│   ├── icon-16.png
│   ├── icon-512.png
│   ├── icon-1024.png
│   └── ...
├── Android/
│   ├── app-icon-512.png
│   ├── mipmap-hdpi/ic_launcher.png
│   ├── mipmap-anydpi-v26/ic_launcher.xml
│   ├── mipmap-hdpi/ic_launcher_foreground.png
│   ├── drawable/ic_launcher_background.xml
│   └── ...
├── iOS/
│   ├── AppStore-1024.png
│   ├── iPhone-180.png
│   └── ...
├── Chrome/
│   ├── icon-128.png
│   ├── small-promo-tile-440x280.png
│   └── ...
├── Favicon/
│   ├── favicon-16x16.png
│   ├── favicon-32x32.png
│   └── apple-touch-icon.png
├── Social/
│   ├── og-image-1200x630.png
│   ├── twitter-card-1200x628.png
│   └── ...
└── Flatpak/
    ├── icon-64.png
    ├── icon-256.png
    └── icon-512.png
```

## Icon previews

Selecting **Android**, **Microsoft Store** or **macOS** opens a live preview of that platform's icon, shown the way the system will draw it: circle and rounded-square launcher masks for Android, light and dark tiles for Windows and macOS.

Each preview has the same controls, and whatever you set is what gets exported:

- **Padding** - adds a safe margin so launchers do not crop your logo.
- **Scale** - 50% to 300%.
- **Drag** the icon to reposition it, or click it and nudge with the arrow keys one pixel at a time.
- **Scroll** the mouse wheel over the preview to scale.
- **Grid** - alignment guides over the preview only, never exported.
- **Reset** - back to the defaults.

The Windows controls apply to every Microsoft Store asset, including the `.ico`. The macOS controls apply to every macOS icon size, where 100% scale matches Apple's grid of 824x824 artwork on a 1024x1024 canvas.

## Screenshots

The **Screenshots** tab resizes existing screenshots onto a store-accepted canvas. Drop in as many as you like, pick **Apple App Store** or **Microsoft Store**, and choose one of that store's accepted sizes. You can set the background colour, and choose whether to pad without enlarging (keeps the picture sharp) or scale up to fill the canvas.

## Options

- **Letterbox (contain)** or **Crop (cover)** - choose how your image fits each target size. For square icons both look the same.
- **Flutter naming convention** - exports iOS and macOS icons with the filenames Flutter expects (e.g. `Icon-App-60x60@2x.png`), so you can drop them straight into a Flutter project.
- **Save as ZIP** - on for a single ZIP, off to write the files into a folder you pick.

## Windows taskbar icons

The `.ico` holds native frames at 16, 20, 24, 30, 32, 36, 40, 48, 64, 96, 128 and 256px. Windows asks for the in-between sizes at different display scalings, so including them keeps the taskbar icon sharp instead of blurred from a resize.

## Microsoft Store - badge logo note

Badge logos must pass [WACK](https://learn.microsoft.com/en-us/windows/uwp/debug-test-perf/windows-app-certification-kit) validation:

- All non-transparent pixels must be **pure white**
- Background must be **transparent**

The app removes the background automatically using dominant-color detection, Otsu thresholding, and foreground cropping, then forces the remaining pixels to white - producing compliant badge logos with no manual editing.

## Android adaptive icons

Selecting Android exports adaptive-icon foreground and background resources alongside the mipmap PNGs, so launchers on Pixel and other devices mask the icon without cropping your logo. Use the preview's Padding and Scale to control how much room the logo gets.

---

The original web version's source is archived under [`/web`](web). Building the app from source is documented in [BUILDING.md](BUILDING.md).

Made by [EERIE](https://eeriegoesd.com).
