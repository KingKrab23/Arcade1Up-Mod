# Arcade1Up LaunchBox Conversion Project

This project converts an old **Arcade1Up NBA Jam** cabinet into a modern emulation arcade powered by **LaunchBox** and **BigBox**. The goal is to reuse the existing cabinet and display while integrating a full Windows-based gaming system that can easily switch between arcade and desktop use.

---

## Project Overview

The cabinet originally had a broken PCB, but the monitor and body were still in good shape. Instead of repairing the stock hardware, the project replaces it with a compact gaming computer setup using an **ASUS ROG Zephyrus G14** laptop as the main system. The laptop connects to a dock inside the cabinet via USB-C, which handles video output, audio, and control inputs. When connected, the cabinet behaves like a dedicated arcade; when unplugged, the laptop remains fully portable.

The system runs **LaunchBox** and **BigBox** for a console-like front end that launches emulators such as RetroArch, Dolphin, PCSX2, Yuzu, and more. All ROMs, BIOS files, and artwork are stored on an external 4TB WD Black drive.

---

## Current Hardware Setup

- **Cabinet:** Arcade1Up NBA Jam (reused monitor, speakers, cabinet shell)
- **Computer:** ASUS ROG Zephyrus G14 (Ryzen 9 8945HS / RTX 4060 / 16 GB RAM / 1 TB SSD)
- **Dock:** HyperDrive Next 6-Port USB-C Hub
- **Storage:** WD Black P10 4TB external HDD
- **Display:** BOE 17” 4:3 LCD connected via HDMI to LVDS controller
- **Audio:** Original Arcade1Up speakers powered by a 12V mini amplifier
- **Frontend:** LaunchBox + BigBox (lifetime license)

---

## Remaining Parts to Purchase

- HDMI to LVDS controller board (for the existing LCD)
- Dual USB encoder kit for two-player controls
- Sanwa-style joystick and button kits
- Small 12V stereo amplifier and splitter cable
- Mounts for controllers and space for a keyboard/mouse
- Optional upgrades: better speakers, cooling fans, and new artwork

---

## System Configuration

- **Operating System:** Windows 11
- **Frontend:** LaunchBox + BigBox
- **Storage Layout:**  
  - E:\LaunchBox → Frontend installation  
  - E:\Emulation\Games → ROMs  
  - E:\Emulation\BIOS → BIOS files  

---

## Planned Layout

Each player will have a joystick and eight buttons, plus smaller Start and Select buttons. There will also be a few admin buttons for pause, menu, coin, and exit functions. The laptop and dock are mounted behind the monitor with proper ventilation and quick disconnect options for maintenance.

---

## Build Progress (as of November 2025)

- ✅ Cabinet shell and monitor available  
- ✅ Laptop and USB-C dock selected  
- 🛒 Next: Order encoder, buttons, amp, and controller board  
- 🔜 Assemble and wire the cabinet, then configure BigBox for arcade mode  

---

## Future Plans

Once the cabinet is functional, optional upgrades may include:
- LED button lighting (via LEDBlinky)
- Trackball or spinner support
- Improved 2.1 audio system
- Custom vinyl graphics or new T-molding
- Small form-factor PC for a dedicated system later on

---

## About

**Start Date:** November 2025  
**Goal:** Fully functional modern arcade cabinet running LaunchBox / BigBox with clean cable management, full two-player setup, and minimal footprint.

