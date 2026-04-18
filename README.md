# 🚌 MacroPeriferico Ruta AR

> A commissioned AR mobile app for the MacroPeriferico public transit system in Guadalajara, México. Users scan their physical transit card to trigger an immersive AR experience — a full animated map of the bus line overlays the card, traces the user's route station by station, and displays the number of stops to their destination.

**Built with:** Unity · AR Foundation · Image Target Tracking · C# · Mobile AR (iOS/Android)

---

## 📹 Demo

> 🎥 [Watch the app in action →](https://www.instagram.com/reels/DIfFE-csFzo/)

---

## ✨ What It Does

The user opens the app and points their phone camera at their MacroPeriferico transit card. The card is recognized as an image target, and a full AR map of the MacroPeriferico bus line appears anchored directly on top of the physical card — stations, route path, and all. The user selects their starting station and destination, and the app animates the route: highlighting each stop along the path and displaying the total number of stations to travel. The entire experience lives in AR, overlaid on the card the user is already holding.

---

## 🛠 How It Works

```
Camera feed → AR Foundation image tracking → transit card recognized as target
     → AR map spawned and anchored to card surface
     → user selects origin + destination stations
     → route animation plays (station-by-station highlight)
     → stop count displayed in AR UI
```

Key technical pieces:

- **Image target tracking** — AR Foundation's tracked image manager recognizes the MacroPeriferico card as a reference image; the AR content anchors to the card's real-world position and orientation and stays locked as the user moves
- **AR map rendering** — the full MacroPeriferico bus line rendered as a 3D-in-world map overlay, scaled to sit cleanly on the card surface
- **Station selection UI** — interactive AR UI panels let the user tap their origin and destination stations directly in world space
- **Route animation** — C# coroutine animates the route sequentially, lighting up each station node along the path from origin to destination
- **Stop counter** — calculates and displays the number of stations between origin and destination as a floating AR label
- **Persistent tracking** — AR content stays anchored to the card even as the user tilts or moves the phone, using AR Foundation's continuous image tracking mode

---

## 📁 Project Structure

```
macroperiferico-ruta-ar/
├── Assets/
│   ├── Scenes/            ← Main AR scene
│   ├── Scripts/           ← C# — tracking manager, route logic, UI controller
│   ├── Prefabs/           ← AR map, station nodes, route path, UI panels
│   ├── ReferenceImages/   ← Transit card image target
│   └── Materials/         ← Station highlight materials, route line renderer
├── Packages/
├── ProjectSettings/
└── README.md
```

---

## 🚀 Running the Project

1. Open in **Unity 2021.3 LTS** or later
2. Ensure **AR Foundation** and **ARCore XR Plugin** (Android) / **ARKit XR Plugin** (iOS) are installed via Package Manager
3. Add your MacroPeriferico card image to the `ReferenceImages` library in AR Foundation
4. Build to a physical iOS or Android device — AR features do not run in the Unity editor
5. Point the camera at the transit card to trigger the experience

---

## 🎯 Context

**Client:** MacroPeriferico public transit system, Guadalajara, México (commissioned via intermediary, 2025).

The brief was to create a wayfinding experience that felt intuitive for everyday transit riders — people who are already holding their card, already thinking about their route. Using the card itself as the trigger made the interaction feel natural rather than requiring a separate marker or QR code. Anchoring the full route map directly on the card surface meant the user could literally trace their journey with their finger in the real world.

The MacroPeriferico is a single BRT (Bus Rapid Transit) line running through Guadalajara's metropolitan area, serving hundreds of thousands of daily riders.

---

## 👤 Author

**Erick García de Anda** — Creative Technologist & Founder, [Nodo Studio](https://www.linkedin.com/in/erickgarciad)

AR/XR · Gesture Interfaces · Interactive Installations · AI Pipelines
