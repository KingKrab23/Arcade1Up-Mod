# 🕹️ LaunchBox / Arcade1Up Conversion – Desktop PC Build (v2, Nov 2025)
### NBA Jam (Wave 3) 4-Player → 2-Player Multicade

This project converts an **Arcade1Up NBA Jam Wave‑3 cabinet** into a **2‑player, 8‑button‑per‑side** multicade running **Windows 11 + LaunchBox/BigBox** on a **desktop PC (Ryzen 5 5500 + Radeon RX 6500 XT)** mounted inside the cab.

This README is meant to live on GitHub and stay **high‑level and structural**.  
For exact part SKUs and price tracking, use the separate **build summary / BOM** document.

---

## 1. Hardware Overview

### 1.1 Cabinet & Display
- **Cabinet:** Arcade1Up NBA Jam (Wave 3, originally 4‑player)
- **Conversion:** 2‑player layout, 8 action buttons per player
- **Monitor:** Stock 17″ 4:3 BOE DV170YGZ‑N10 LCD
- **Driver:** LVDS → HDMI controller board powered from the original 12 V brick

### 1.2 Main System – Desktop PC (Inside Cabinet)
- **Form factor:** ATX/mid‑tower desktop mounted in lower cavity above riser
- **CPU:** AMD Ryzen 5 5500 (6C/12T)
- **GPU:** AMD Radeon RX 6500 XT 4 GB
- **RAM:** 16 GB DDR4 (XMP 3200–3600 MHz enabled in BIOS)
- **Storage (internal):** 1 TB PCIe NVMe SSD for Windows + core software
- **Storage (external):** WD Black P10 4 TB USB HDD for ROMs / BIOS / media
- **OS:** Windows 11 Home
- **Use cases:**
  - Retro emulation (8‑bit → PS3 / X360 / Switch where feasible)
  - BigBox frontend
  - PC Gaming as available

### 1.3 Controls
- 2 × arcade joysticks (8‑way)
- 16 × 30 mm action buttons (8 per player)
- 4 × 30 mm admin buttons (Start, Select, Coin, Exit – configurable)
- 2 × Zero‑Delay USB encoders (one per player)
- 2 × 2.4 GHz wireless “PS3‑style” gamepads + USB dongle (optional couch play)

### 1.4 Audio
- USB‑powered soundbar mounted under the marquee or control deck
- 3.5 mm audio from PC → ground‑loop isolator → soundbar
- Optionally, stock A1Up speakers + small 12 V stereo amp

### 1.5 Power & Wiring
- Internal 6‑outlet surge strip mounted on cabinet floor:
  - Desktop PC
  - LVDS/HDMI board
  - USB soundbar and/or 12 V amp
- Existing 12 V Arcade1Up brick reused for monitor (and amp via splitter if used)
- Optional rear “master kill switch” on power strip or inline

---

## 2. System Architecture

### 2.1 User Accounts & Security
Two Windows accounts:

1. **Admin account (you)**
   - Microsoft account sign‑in allowed
   - Only administrator on the box
   - Used for:
     - Installing software
     - Updating emulators
     - Changing system settings

2. **Arcade account (kids / guests)**
   - Local standard user (no Microsoft sign‑in)
   - Auto‑login enabled
   - BigBox launched at sign‑in and locked in **kiosk mode**
   - Cannot install apps or change system settings without admin password

General rules:
- **UAC ON** and at default level
- Kids use **only** the Arcade account
- Exiting BigBox or opening BigBox options requires a password

### 2.2 Directory Layout

The goal is to keep **emulators on C:** (fast SSD) and **ROMs/media on the external drive**.

**Internal SSD:**
```text
C:\Emulation\
 ├─ Emulators\          # All emulator binaries/tools
 │   ├─ RetroArch\
 │   ├─ Dolphin\
 │   ├─ PCSX2\
 │   ├─ RPCS3\
 │   ├─ Xenia\
 │   ├─ Ryujinx\
 │   └─ ... (others)
 ├─ Tools\              # Supporting tools, scripts, configs
 └─ Config\             # Centralized configs if desired
```

**External HDD (fixed drive letter, e.g. X:):**
```text
X:\LaunchBox\          # Frontend (can live here or on C:)
X:\Emulation\
 ├─ BIOS\               # Per‑system BIOS
 └─ Games\
     ├─ NES\
     ├─ SNES\
     ├─ N64\
     ├─ PS2\
     ├─ PS3\
     ├─ Switch\
     ├─ MAME\
     └─ ...
```

Windows Disk Management should be used to **pin the external drive letter** so LaunchBox paths don’t break.

### 2.3 Frontend & Emulators

**Frontend:**
- LaunchBox for configuration
- BigBox for cabinet mode (4:3 theme, kiosk mode, controller‑friendly)

**Core emulators (not exhaustive):**
- RetroArch (NES, SNES, GB/GBC/GBA, PS1, etc.)
- DuckStation (alt PS1)
- Dolphin (GameCube/Wii)
- PCSX2 (PS2)
- RPCS3 (PS3)
- Xenia (Xbox 360)
- Ryujinx / Yuzu forks (Switch)
- Citra / Lime3DS (3DS)
- MAME (arcade)
- Others as needed

---

## 3. Software Install Automation (Scoop Script)

A **Scoop‑based setup script** is used to install and update emulators on Windows in a repeatable way.

### 3.1 Script Concept

- Lives in this repo under something like:
  ```text
  /software/emulator_setup.sh
  ```
- Intended to be run from **Git Bash** or WSL on Windows.
- Uses **Scoop** to:
  - Add the emulation bucket(s)
  - Install emulators into `C:\Emulation\Emulators\`
  - Optionally pin versions for stability
  - Provide update commands

### 3.2 High‑Level Behavior (Pseudo‑Spec)

SEE: https://github.com/KingKrab23/scoop-install-emulators for a sibling repo that will handle the below

1. Ensure **Scoop** is installed (or install it).
2. Add any required buckets:
   - `main`, `extras`, and an emulation bucket if used.
3. Install or update packages such as:
   - `retroarch`
   - `dolphin`
   - `pcsx2`
   - `rpcs3`
   - `xenia-canary` (if available)
   - `ryujinx`
   - `citra-emu` / `lime3ds`
   - Supporting tools (7-Zip, Notepad++, etc.).
4. Move/copy the installed folders to:
   - `C:\Emulation\Emulators\<EmulatorName>`
5. Print a summary of:
   - What was installed
   - Where it lives
   - How to run `scoop update` / `scoop update <pkg>`

> The README doesn’t duplicate the entire script; the script itself should be authoritative.  
> This section simply documents its existence, purpose, and directory assumptions.

---

## 4. Cabinet Layout & Mounting

### 4.1 PC Placement

- Tower stands vertically in the **main lower cavity above the riser**.
- Constraints:
  - Internal width ~19.75″
  - Depth ~22.8″ (PC depth ~17–18″ is fine)
- Rear of PC faces the **cabinet’s rear service door** for:
  - Access to HDMI, USB ports, and power
  - Pressing the power button if needed

### 4.2 Cooling & Ventilation

- Leave space behind and above the PC for intake/exhaust.
- Options:
  - Add a **120 mm exhaust fan** on the rear panel
  - Add vent holes under the control deck if temps are high
- Keep cable bundles away from PC intake/exhaust fans.

### 4.3 Controls & Wiring

- Control deck:
  - 20 × 30 mm holes (16 player buttons + 4 admin)
  - 2 joysticks underneath, centered on player positions
- Wiring:
  - Each button → Zero‑Delay encoder input
  - Encoders → USB‑A ports on PC
  - Cables bundled with zip ties and adhesive clips along side panels

### 4.4 Video & Audio Wiring

- **Video:**
  - GPU HDMI → LVDS controller HDMI input
  - LVDS board → LCD via stock ribbon cable
- **Audio:**
  - PC 3.5 mm → ground loop isolator → soundbar 3.5 mm input
  - Soundbar USB → cabinet power strip (or PC USB)

---

## 5. Windows & BigBox Behavior

### 5.1 Windows Configuration (Arcade Account)

- Auto‑login to Arcade user
- Disable:
  - Screen saver
  - Sleep / hibernate
  - Lock screen timeout (or set very high)
- Privacy:
  - Turn off extra telemetry, tailored ads, and unnecessary app permissions

### 5.2 BigBox Configuration

- Theme optimized for **4:3** (no ultrawide UI elements)
- Kiosk mode enabled:
  - Exit and Options require password
- Startup:
  - BigBox launched on Arcade login (Startup folder or Task Scheduler)
- Shutdown flow:
  - Admin can trigger system shutdown from BigBox menu
  - Or use a mapped admin combo/button to exit BigBox when needed

---

## 6. Build Phases & Current Status

### Phase 1 – Planning & Parts (Done)
- Cabinet acquired
- Core PC selected and tested
- Controls and encoders purchased
- LVDS controller and audio solution chosen

### Phase 2 – PC Setup (In Progress)
- BIOS configured (XMP, CPPC, sensible fan curves)
- Windows 11 installed and updated
- Drivers: AMD chipset + Radeon Adrenalin + audio/LAN
- Admin + Arcade accounts created
- Privacy settings tuned

### Phase 3 – Software Stack (In Progress)
- Scoop script defined and iterated on
- LaunchBox/BigBox installed and activated
- Emulators installed to `C:\Emulation\Emulators\`
- ROMs and BIOS organized on `X:` external drive
- One “test game” verified per major system

### Phase 4 – Cabinet Integration (Upcoming)
- Control deck fully wired and tested
- LVDS controller mounted and configured
- PC mounted, power strip installed
- HDMI/USB/audio routed and tied down

### Phase 5 – Polish & Extras (Future)
- Artwork / vinyl
- Cooling fan(s) and noise tuning
- Optional GPU upgrade (e.g., RX 6600 / 6700 XT) if needed for heavier PC gaming
- Additional QoL scripts (backup configs, sync save data, etc.)

---

## 7. Repository Structure (Suggested)

```text
/README.md                              # This document
/docs/
  ├─ cabinet_layout.md                  # Mounting diagrams, measurements
  ├─ wiring_diagram.md                  # Control + power wiring
  └─ software_notes.md                  # Emulator quirks, per‑system notes
/hardware/
  ├─ bom_summary.md                     # Human‑readable BOM (no prices)
  └─ panel_specs.md                     # Monitor & control panel specs
/software/
  ├─ emulator_setup.sh                  # Scoop‑based installer script
  ├─ bigbox_profile/                    # Themes, settings backups
  └─ configs/                           # Example config files
/assets/
  ├─ marquee/                           # Artwork
  └─ control_deck/                      # Deck art, button layout templates
```

This README should stay **evergreen** as the top‑level orientation for the project.  
Details (script flags, exact emulators, theme choices) should be documented in the `/software` and `/docs` sub‑files as they evolve.
