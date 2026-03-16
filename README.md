# CMX Widget 🎨

A CMX-style HUD/tech widget app for iOS built with SwiftUI and WidgetKit. Inspired by the popular CMX KLWP presets for Android.

---

## Features
- 4 built-in CMX-style presets (HUD Z, Klean Tek, Lab UI, Minimal Arc)
- Live time and date display on widgets
- Customizable accent colors and backgrounds
- Preset editor with real-time preview
- Home screen widgets (small, medium, large)
- Dark mode optimized UI

---

## Requirements
- macOS with Xcode 15+
- iOS 18.0+
- Apple Developer Account (free for personal use)

---

## Roadmap
- [ ] Lock screen widget support
- [ ] Music / Now Playing integration
- [ ] Battery indicator
- [ ] Weather data integration
- [ ] Preset sharing (export/import)
- [ ] More preset styles

---

# CMX Widget - iOS Setup Guide

## Project Structure
```
CMXWidget/
├── CMXWidgetApp.swift              ← App entry point
├── Models/
│   └── CMXPreset.swift             ← Preset data model
├── Views/
│   ├── ContentView.swift           ← Main UI (preset selector)
│   ├── CMXWidgetFace.swift         ← Widget face designs (HUD Z, Lab UI, etc.)
│   └── PresetEditorView.swift      ← Customizer UI
└── Widget/
    └── CMXWidget.swift             ← WidgetKit extension
```

---

## Xcode Setup Steps

### 1. Create the Xcode Project
1. Open Xcode → **Create New Project**
2. Choose **iOS → App**
3. Product Name: `CMXWidget`
4. Bundle ID: `com.yourname.cmxwidget`
5. Interface: **SwiftUI** | Language: **Swift**
6. Click **Next** and save

### 2. Add Widget Extension
1. File → **New → Target**
2. Choose **Widget Extension**
3. Name it: `CMXWidgetExtension`
4. ✅ Check "Include Configuration Intent"? → **No**
5. Click **Finish** → **Activate** when prompted

### 3. Add App Group (for shared data)
1. Select your main app target → **Signing & Capabilities**
2. Click **+** → **App Groups**
3. Add: `group.com.yourname.cmxwidget`
4. Do the same for the **Widget Extension** target

### 4. Add the Files
- Copy each `.swift` file from this package into the correct folder in Xcode
- Make sure `CMXWidget.swift` is in the Widget Extension target
- All other files belong to the main app target

### 5. Fix Shared Files
- `CMXPreset.swift` and `CMXWidgetFace.swift` need to be in **both targets**
- In Xcode: select the file → check both targets in the **Target Membership** panel (right sidebar)

### 6. Run on Device
1. Connect your iPhone via USB
2. Select your device in the top bar
3. Press **▶ Run**
4. On your iPhone: long-press home screen → **+** → search "CMX Widget" → add it

---

## Customization

### Add a New Style
1. Add a case to `CMXStyle` enum in `CMXPreset.swift`
2. Create a new `Face` struct in `CMXWidgetFace.swift`
3. Add the case to the switch in `CMXWidgetFace`

### Add New Colors
Edit the color arrays in `PresetEditorView.swift`

---

## Next Features to Build
- [ ] Lock screen widget support
- [ ] Music/Now Playing integration
- [ ] Battery indicator
- [ ] Weather data
- [ ] Preset sharing (export/import)
