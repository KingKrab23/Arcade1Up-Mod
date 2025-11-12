# 🕹️ Arcade1Up → LaunchBox Conversion (BigBox Cabinet Build)

A project to repurpose an **Arcade1Up NBA Jam** cabinet into a full Windows-based **LaunchBox / BigBox** arcade system powered by an **ASUS ROG Zephyrus G14** laptop.

---

## 🎯 Project Goals
- Convert a broken Arcade1Up cabinet into a fully functional emulation station.
- Use LaunchBox + BigBox as the unified frontend.
- Maintain a clean, self-contained setup (single USB-C connection).
- Support **two-player / 8-button** control layout.
- Keep future upgradability (mini-PC or NUC) in mind.

---

## ✅ Hardware You Already Have
- **Arcade1Up NBA Jam cabinet** – intact shell and LCD  
- **ASUS ROG Zephyrus G14** – Ryzen 9 8945HS / RTX 4060 / 16 GB RAM / 1 TB SSD  
- **HyperDrive Next 6-Port USB-C Hub** – HDMI, USB-A x 2, PD input, SD/microSD  
- **WD Black P10 4 TB** external HDD – ROMs, BIOS, artwork  
- **Arcade1Up 12 V power brick**  
- **BOE DV170YGZ-N10 17″ 4:3 LCD panel**  
- **Stock Arcade1Up speakers**  
- Possibly reusable buttons/joysticks  
- **Lifetime LaunchBox + BigBox + EmuMovies licenses**

---

## 🧩 Parts Still Needed
| Part | Purpose | Est. Price |
|------|----------|-----------:|
| HDMI → LVDS controller board (for DV170YGZ-N10) | Laptop → LCD connection | $25–30 |
| Dual USB encoder kit (Xin-Mo / Zero Delay) | Interface for 2-player controls | $15–25 |
| 12 V mini stereo amp (TPA3116/PAM8610) | Drive speakers | $8–15 |
| New 2.0 or 2.1 speakers (optional) | Audio upgrade | $20–40 |
| Sanwa-style 2-player joystick + 8 buttons | Main controls | ≈ $40 |
| 24 mm buttons (Start/Select/Menu) | Admin controls | ≈ $10 |
| 12 V DC splitter / adapter | Power amp + display | $5 |
| Controller hooks / mounts | Store gamepads | $10–20 |
| Keyboard / mouse tray or slot | Maintenance access | $20–30 |
| (Optional) 17–19″ 4:3 HDMI monitor | Backup display option | $80–120 |
| (Optional) Custom vinyl artwork | Cabinet refresh | $30–60 |

---

## 💻 System Configuration
**OS:** Windows 11  
**Frontend:** LaunchBox + BigBox  
**Emulators:** RetroArch, RPCS3, Yuzu, Ryujinx, Dolphin, PCSX2, Cemu, Citra …  
**Storage:** WD Black P10 (E:\)  
**Display:** Arcade LCD via HDMI → LVDS  
**Audio:** 12 V amp → Arcade1Up speakers  

### Dock / Connectivity
- Single USB-C to hub for all I/O  
- HDMI out → LVDS board  
- USB-A → encoders / amp  
- Optional SD card slot for quick asset transfer  

---

## 🎮 Control Layout
- 2 Players × 8 Buttons (30 mm) each  
- Start/Select (24 mm) per player  
- Admin buttons: Pause/Menu, Coin, Exit, optional hidden Shutdown  
- ~1.25″ button spacing, joystick ≈ 3.5–4″ from first button column  

---

## 🧱 Mounting & Ventilation
### Laptop
- Mounted on rear slide-out tray or shelf  
- 2–3″ air gap for ventilation  
- Velcro straps or rubber pads to secure  
- Power brick on internal strip / surge protector  
- Cable pass-through with rubber grommets  

### Dock
- Mounted with Velcro / 3 M strips to side panel  
- Short HDMI + USB runs to display and encoders  
- Cable clips for clean routing  
- Optional USB fan if > 35 °C inside  

### Power
- Laptop charger separate  
- Amp + display share 12 V brick via splitter  
- Inline fuse or rear kill-switch recommended  

---

## ⚙️ Software Setup
```
E:\LaunchBox\
 ├─ Emulators\
 │   └─ RetroArch\
 ├─ Emulation\
 │   ├─ BIOS\
 │   └─ Games\<Platform>\
```
LaunchBox, BigBox, and EmuMovies licenses already activated.

---

## 🛠️ Setup Sequence
1. Buy LVDS controller board.  
2. Buy dual USB encoder kit.  
3. Buy 12 V stereo amp + splitter.  
4. Buy joystick + button kit.  
5. (Optional) Add controller hooks / keyboard slot / artwork.  
6. Mount dock → connect HDMI + USB → test display and controls.  
7. Configure BigBox autostart on boot.  

---

## 💡 Future Ideas
- LEDBlinky integration for button lighting  
- Trackball / spinner module  
- 2.1 speaker upgrade  
- Front USB service port or power toggle  
- Cooling fan mod  
- New T-molding / acrylic bezel art  
- Dedicated mini-PC upgrade later  

---

## 🧾 Current Status (Nov 2025)
- ✅ Laptop selected  
- ✅ Dock purchased  
- 🛒 Next → buy controller board / encoders / amp / buttons  
- 🔜 Integrate dock and test cabinet wiring + software  

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

### License
MIT License — free for personal and educational use.

---

### Author
**Tony** – Software Engineer / DIY Arcade Builder  
📅 Project start: 2025-11  
