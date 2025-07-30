🕹️ Spec Deck – Left Controller
Modular Gamepad | 3D Models + PCB + Firmware

This folder contains all the files for the Left Controller of the Spec Deck modular handheld, including:

🧩 3D-printable case and button files

📐 PCB schematic, layout, and BOM

🔧 ESP32-S3 firmware located under main/

📦 Folder Structure
/3D Files/
Printable case parts:


Optimized for FDM printing (PLA/PETG, 0.2 mm layer height, 0.15 mm tolerances).

/PCB Files/
Hardware design files:


The PCB includes:

ESP32-S3 module

USB-C data and charging

BQ25302 charger

Hall-effect triggers

JST battery input

Support for RGB LEDs and rumble

/Firmware/
Firmware source code for the ESP32-S3.

Includes:

BLE + USB HID support

Dock detection and auto pairing

Battery monitoring and charging control

RGB LED and rumble motor support

🔧 Flashing Instructions
You can flash the firmware in two ways:

Option 1: Using ESP-IDF (Developer Mode)
Make sure you have ESP-IDF v5.x installed.
Run the following:

bash
Copy
Edit
idf.py set-target esp32s3
idf.py build
idf.py -p /dev/ttyUSB0 flash monitor
Hold BOOT during power-up to enter download mode if needed.

Option 2: Using the Spec Deck Companion App (Recommended)
The Companion App includes a flashing tool with automatic USB port detection and firmware version selection.

Connect the controller via USB-C

Open the Companion App

Go to Firmware > Flash Left Controller

Select the version or upload a .bin

Click Flash and wait for confirmation

This method is beginner-friendly and includes error logs and update history.

🛠️ Assembly Notes
Secure PCB and battery inside the frame

Connect hall triggers, rumble motor, and RGB LEDs if used

Close shell and secure with M2 screws

Connect via USB or pair via BLE

🔋 Power Specs
Battery: 1S 3.7 V Li-ion (JST-PH)

Charging via USB-C up to 1 A

Runtime and charge reporting over HID

Fully usable while charging