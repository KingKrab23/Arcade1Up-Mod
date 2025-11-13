# 🕹️ LaunchBox / Arcade1Up Conversion – High-Level Overview  
### NBA Jam (Wave 3) 4-Player → 2-Player Conversion

This project converts an **Arcade1Up NBA Jam 4-player Wave-3 cabinet** into a **2-player** LaunchBox/BigBox multicade powered by a **Windows laptop**.  
This README stays **high-level** and focuses on **structure and design**, not individual SKUs or prices.

For detailed part numbers, vendors, and pricing, use the dedicated **BOM / build summary** document instead.

---

## 1. Project Structure

- **Cabinet Base:**  
  - Arcade1Up NBA Jam (Wave 3, originally 4-player)  
  - Converted to a **2-player, 8-button-per-side** layout

- **Brain of the System:**  
  - Laptop (inside or outside cabinet) as the main PC  
  - Single USB-C dock for video + controls + audio

- **Frontend & Software:**  
  - Windows 11  
  - LaunchBox + BigBox  
  - RetroArch plus selected standalone emulators  

---

## 2. Hardware Overview

### 2.1 Existing / Core Hardware
- Arcade1Up cabinet with stock LCD  
- ASUS ROG Zephyrus G14 laptop  
- USB-C dock/hub  
- External HDD for ROMs/BIOS/media  
- Lifetime LaunchBox + BigBox + EmuMovies licenses

### 2.2 Control System
- 2-player joystick + button setup  
- Dual USB encoders  
- Admin buttons: Start / Select / Coin / Exit  
- Wave-3 compatible 2-player deck with plexi top

### 2.3 Video & Audio
- LVDS → HDMI controller for stock monitor  
- USB/amp-powered speakers or soundbar  
- Noise isolator if needed

### 2.4 Power & I/O
- Internal power strip  
- 12 V brick reused for monitor and/or amp  
- Panel-mount USB extensions for easy access

---

## 3. High-Level System Architecture

### 3.1 Data & Compute
- **Laptop** runs OS, LaunchBox, and emulators  
- **External drive** stores:
  - `LaunchBox`  
  - `Emulation\\BIOS`  
  - `Emulation\\Games\\<Platform>`  

### 3.2 Video Path
Laptop HDMI → USB-C dock → LVDS controller → Stock LCD

### 3.3 Audio Path
Laptop 3.5 mm → (optional isolator) → speakers/soundbar  
Powered via USB or internal strip

### 3.4 Controls Path
Control deck → dual USB encoders → dock → laptop  
Optional wireless controllers via USB dongle

### 3.5 External I/O
Panel-mount USB ports → dock/encoders  
Allows connection of controllers, keyboard/mouse, USB sticks

---

## 4. Cabinet Layout & Mounting (Conceptual)

### 4.1 Control Deck
- 8 main buttons per player  
- Joysticks mirrored  
- Admin button row  
- Cleanly routed wiring  

### 4.2 Internal Layout
- LVDS controller near monitor  
- Dock on a side panel  
- Power strip on cabinet floor  
- Cable management with clips/zip ties  

### 4.3 Laptop Placement (Options)
- Mounted inside on shelf or tray  
- OR outside with a simple 3-cable “umbilical”  
- Easy to disconnect and use independently  

---

## 🧱 Mounting & Ventilation

### Laptop
- Rear shelf or slide-out tray  
- 2–3″ ventilation gap  
- Velcro straps or rubber pads  
- Power brick on internal strip  
- Cable pass-through with grommets  

### Dock
- Mounted with Velcro/3M strips  
- Short HDMI + USB lines  
- Cable clips for clean routing  
- Optional small USB fan if cabinet exceeds ~35 °C  

### Power
- Laptop charger runs separately  
- Amp + display can share 12 V brick via splitter  
- Inline fuse or rear kill-switch recommended  

---

## 5. Software Layout & Behavior

### 5.1 Directory Layout
```
E:\\LaunchBox\\
 ├─ Emulators\\
 │   └─ RetroArch\\
 ├─ Emulation\\
 │   ├─ BIOS\\
 │   └─ Games\\<Platform>\\
```

### 5.2 Frontend Behavior
- BigBox boots directly into arcade mode  
- Arcade-optimized theme  
- Unified input mapping across all platforms  
- Admin buttons mapped to Pause / Menu / Exit  

### 5.3 Input Mapping
- Standardized 8-button layout for fighters  
- Consistent Start/Select per system  
- Admin buttons mapped globally  

---

## ⚙️ Software Setup Summary
- Install LaunchBox + BigBox on external drive  
- Configure RetroArch and standalone emulators  
- Map controls to match physical deck  
- Configure BigBox for auto-launch  

---

## 📂 Repository Structure
```
/docs               → diagrams, mounting plans  
/hardware           → specs, wiring notes, BOM  
/software           → configs, emulator presets  
/assets             → marquee, artwork, theme files  
PROJECT_OVERVIEW.md → this document  
```

---

## 6. Build Phases (High Level)

1. **Control Deck Prep** – Install controls, wire to encoders  
2. **Video & Audio** – Install LVDS board and speakers  
3. **Internal Wiring** – Mount dock, power strip, and route cables  
4. **Software Setup** – Configure LaunchBox/BigBox, map controls  
5. **Polish** – Cable management, optional artwork/cooling  
