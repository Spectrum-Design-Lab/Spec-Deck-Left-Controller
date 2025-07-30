# 🕹️ Spec Deck – Left Controller  
**Modular Gamepad | 3D Models + PCB + Firmware**

This folder contains all the files for the **Left Controller** of the Spec Deck modular handheld, including:

- 🧩 3D-printable case and button files  
- 📐 PCB schematic, layout, and BOM  
- 🔧 ESP32-S3 firmware source code under `Firmware/`

---

## 📦 Folder Structure

### `/3D Files/`  
Printable case parts:

- `shell_top.stl` – Top enclosure shell  
- `shell_bottom.stl` – Bottom shell with grip  
- `dpad.stl` – Directional pad  
- `trigger_l1.stl`, `trigger_l2.stl` – Shoulder and trigger parts  
- `mount_frame.step` – Internal frame for PCB and battery

Optimized for FDM 3D printing (PLA or PETG, 0.15–0.2 mm layers, tuned for ~0.2 mm tolerances).

---

### `/PCB Files/`  
All files needed to fabricate the Left Controller PCB:

- `left_controller.kicad_pro` – KiCad project file  
- `left_controller.sch` – Electrical schematic  
- `left_controller.kicad_pcb` – Board layout  
- `gerbers/` – Ready-to-upload Gerber files  
- `bom.csv` – Bill of materials with manufacturer part numbers  
- `pick_and_place.csv` – For automated SMT assembly

Includes:

- ESP32-S3 microcontroller  
- USB-C for data + charging  
- BQ25302 charger (1 A max input)  
- JST battery connector  
- Support for rumble, hall triggers, and RGB LEDs

---

### `/Firmware/`  
Firmware source code (ESP-IDF based):

- BLE + USB HID input  
- Dock detection and auto-sync  
- Rumble motor and RGB LED control  
- Battery monitoring and charging feedback  
- Configurable inputs (D-Pad, triggers, shoulder buttons)

---

## 🔧 Flashing Instructions

You can flash the controller firmware using:

### ✅ Option 1: Spec Deck Companion App (Recommended)  
Use the flashing window in the Companion App for easy updates:

1. Connect the Left Controller via USB-C  
2. Open the **Spec Deck Companion App**  
3. Navigate to **Firmware > Flash Left Controller**  
4. Choose from available firmware versions (via GitHub) or upload your own `.bin`  
5. Click **Flash** — logs and success confirmation will be displayed

This method is safest and simplest for most users.

---

### 🧪 Option 2: Manual Flash via ESP-IDF  
For developers and advanced users:

```bash
idf.py set-target esp32s3
idf.py build
idf.py -p /dev/ttyUSB0 flash monitor
