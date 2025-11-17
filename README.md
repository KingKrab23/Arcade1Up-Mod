# 🕹️ LaunchBox / Arcade1Up Conversion – High-Level Overview
### NBA Jam (Wave 3) 4-Player → 2-Player Conversion

This project converts an **Arcade1Up NBA Jam 4-player Wave-3 cabinet** into a **2-player** LaunchBox/BigBox multicade powered by an **ASUS ROG Ally Z2 “Xbox Edition”** as the main PC instead of a traditional laptop.
This README stays **high-level** and focuses on **structure and design**, not individual SKUs or prices.

For detailed part numbers, vendors, and pricing, use the dedicated **BOM / build summary** document instead.

---

## 1. Project Structure

- **Cabinet Base:**
  - Arcade1Up NBA Jam (Wave 3, originally 4-player)
  - Converted to a **2-player, 8-button-per-side** layout

- **Brain of the System:**
  - **ROG Ally Z2 “Xbox Edition”** as the main PC
  - Single USB-C dock/hub for video + controls + audio

- **Frontend & Software:**
  - Windows 11
  - LaunchBox + BigBox
  - RetroArch plus selected standalone emulators

---

## 2. Hardware Overview

### 2.1 Existing / Core Hardware
- Arcade1Up cabinet with stock 17″ 4:3 LCD
- ASUS ROG Ally Z2 – Xbox Edition
- USB-C dock/hub (HyperDrive Next or similar)
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
- **ROG Ally Z2** runs:
  - Windows 11
  - LaunchBox + BigBox
  - RetroArch and standalone emulators
- **External drive** stores:
  - `LaunchBox`
  - `Emulation\BIOS`
  - `Emulation\Games\<Platform>`

### 3.2 Video Path
ROG Ally USB-C → USB-C dock → HDMI → LVDS controller → Stock 4:3 LCD

### 3.3 Audio Path
ROG Ally 3.5 mm (or USB audio) → (optional isolator) → speakers/soundbar  
Speakers powered via USB or internal power strip

### 3.4 Controls Path
Control deck → dual USB encoders → dock → ROG Ally  
Optional wireless controllers via USB dongle on dock

### 3.5 External I/O
Panel-mount USB ports → dock/encoders  
Allows connection of controllers, keyboard/mouse, USB sticks

---

## 4. Cabinet Layout & Mounting (Conceptual)

### 4.1 Control Deck
- 8 main buttons per player
- Joysticks mirrored
- Admin button row
- Cleanly routed wiring with zip ties and adhesive clips

### 4.2 Internal Layout
- LVDS controller near the monitor
- Dock on a side panel for short cable runs
- Power strip on cabinet floor
- Cable management with clips/zip ties

### 4.3 ROG Ally Placement (Options)
- Mounted **outside** on a side bracket/stand (primary plan)
- OR on a small shelf/tray next to the cabinet with a single USB-C “umbilical”
- Easy to disconnect and use independently as a handheld

---

## 🧱 Mounting & Ventilation

### ROG Ally
- Cradle or stand on cabinet side or nearby surface
- Vents kept clear (no sealed box)
- USB-C cable routed cleanly to dock
- Optional Velcro strap, lip, or stopper to prevent falls

### Dock
- Mounted with Velcro/3M strips inside cabinet
- Short HDMI + USB runs to monitor, encoders, and audio
- Cable clips for clean routing
- Optional small USB fan if cabinet runs hot

### Power
- ROG Ally charger plugged into internal or nearby power strip
- Amp + display can share 12 V brick via splitter
- Inline fuse or rear kill-switch recommended for safety

---

## 5. Software Layout & Behavior

### 5.1 Directory Layout
```text
E:\LaunchBox\
 ├─ Emulators\
 │   └─ RetroArch\
 ├─ Emulation\
 │   ├─ BIOS\
 │   └─ Games\<Platform>\
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
- Install LaunchBox + BigBox on the external drive used by the ROG Ally
- Configure RetroArch and standalone emulators
- Map controls to match the physical deck layout
- Configure BigBox to auto-launch at Windows login on the Ally

---

## 📂 Repository Structure
```text
/docs               → diagrams, mounting plans
/hardware           → specs, wiring notes, BOM
/software           → configs, emulator presets
/assets             → marquee, artwork, theme files
README.md           → this document
```

---

## 6. Build Phases (High Level)

1. **Control Deck Prep** – Install controls, wire to encoders
2. **Video & Audio** – Install LVDS board and speakers/soundbar
3. **Internal Wiring** – Mount dock, power strip, and route cables
4. **Software Setup** – Configure LaunchBox/BigBox on ROG Ally, map controls
5. **Polish** – Cable management, optional artwork/cooling
