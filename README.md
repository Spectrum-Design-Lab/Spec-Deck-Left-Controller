# 🕹️ Spec Deck – Left Controller  
**Modular Gamepad | 3D Models + PCB + Firmware**

This folder contains all the files for the **Left Controller** of the Spec Deck modular handheld, including:

- 🧩 3D-printable case and button files  
- 📐 PCB project in EasyEDA format + BOM  
- 🔧 ESP32-S3 firmware source code under `Firmware/`

> 🚧 All folders currently contain **placeholder files**. Final files will be published at launch.  
> 🔄 **File names and structure may change** before final release.

---

## 📦 Folder Structure

### `/3D Files/`  
**Status: Placeholder**  
Final folder will include:

- `shell_top.stl` – Top enclosure shell  
- `shell_bottom.stl` – Bottom shell with grip  
- `dpad.stl` – Directional pad  
- `trigger_l1.stl`, `trigger_l2.stl` – Shoulder and trigger parts  
- `mount_frame.step` – Internal frame for PCB and battery

Optimized for FDM 3D printing (PLA or PETG, 0.15–0.2 mm layers, ~0.2 mm tolerance).

---

### `/PCB Files/`  
**Status: Placeholder**  
Final folder will include:

- `Spec Deck Left Controller.epro` – EasyEDA project file  
- `bom.csv` – Bill of Materials with part numbers

This board includes:

- ESP32-S3 microcontroller  
- USB-C for data + charging  
- BQ25302 charger (1 A max input)  
- JST battery connector  
- Support for hall triggers, RGB LEDs, and rumble

> Gerber files will be exportable from the EasyEDA project after launch.

---

### `/Firmware/`  
**Status: Placeholder**  
Final folder will include ESP32-S3 firmware source code (ESP-IDF based):

- BLE + USB HID gamepad support  
- Dock detection and auto-sync  
- Battery monitoring and charging feedback  
- Rumble motor and RGB LED control  
- Configurable inputs (D-Pad, shoulder triggers, hall effects)

---

## 🔧 Flashing Instructions

You can flash the controller firmware using:

### ✅ Option 1: Spec Deck Companion App (Recommended)  
Use the built-in flashing window for simple updates:

1. Connect the Left Controller via USB-C  
2. Open the **Spec Deck Companion App**  
3. Navigate to **Firmware > Flash Left Controller**  
4. Choose a version from GitHub or upload a `.bin`  
5. Click **Flash** – monitor the status and logs

---

### 🧪 Option 2: Manual Flash via ESP-IDF  
For developers or advanced users:

```bash
idf.py set-target esp32s3
idf.py build
idf.py -p /dev/ttyUSB0 flash monitor
```

## 🛠️ Assembly Instructions  
📦 Full assembly guide will be released at launch.

**Basic overview:**

- 3D print the shell and internal frame parts  
- Assemble the PCB using the provided BOM  
- Connect JST battery, triggers, RGB LED, and rumble motor  
- Flash the firmware before closing the case  
- Mount everything into the internal frame and secure using M2 screws  
- Test functionality via USB or BLE connection

---

## 🔋 Power Specs

- **Battery:** 1S Li-ion (3.7 V nominal) with JST-PH connector  
- **Charging:** USB-C via BQ25302, max 1 A input  
- System is fully usable during charge  
- Battery level and charge state reported via USB/BLE HID interface  
- Rumble and LED draw powered from system 3.3 V rail

