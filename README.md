🕹️ Xbox 360 Wireless Gamepad to Bluetooth Converter (ESP32 Hack)
This project revives a broken Xbox 360 wireless controller by replacing its internals with an ESP32 that emulates a Bluetooth HID gamepad. All original buttons, sticks, and triggers are wired to the ESP32, which connects seamlessly to PCs, Android devices, and emulators over Bluetooth.

💡 Why?
Xbox 360 wireless controllers are great, but when the RF module or logic board dies, they're hard to fix. Instead of throwing it away, this project gives the shell and buttons a second life—now as a Bluetooth controller with modern BLE compatibility.

🛠️ Hardware Used
Component	Details
ESP32 Devkit V1	The brain of the new controller
Xbox 360 Controller Shell	Reused for ergonomics and button placement
Tactile switches or original PCB pads	For D-Pad, ABXY, triggers, etc.
Analog sticks	Wired directly to ESP32 ADCs
TP4056 module + LiPo (Optional)	For rechargeable wireless use
Jumper wires, glue, heatshrink	For internal wiring and clean install

🔌 Button Mapping Plan
Xbox Button	ESP32 Pin	Notes
D-Pad Up	GPIO 32	Digital input (pulled up)
D-Pad Down	GPIO 33	〃
D-Pad Left	GPIO 25	〃
D-Pad Right	GPIO 26	〃
A	GPIO 27	〃
B	GPIO 14	〃
X	GPIO 12	〃
Y	GPIO 13	〃
Start	GPIO 18	〃
Back	GPIO 19	〃
LB / RB	GPIO 5/17	〃
LT / RT	GPIO 34/35	Analog triggers (optional)
Left Stick X/Y	GPIO 36/39	Analog
Right Stick X/Y	GPIO 2/4	Analog
Stick Clicks	GPIO 21/22	Digital input

📲 Software Setup
Libraries
Install this library:

ESP32-BLE-Gamepad

Uploading
Open Arduino IDE / PlatformIO

Select ESP32 Dev Module

Upload your customized firmware

Open Bluetooth settings on host device and pair with ESP32 Gamepad

🧠 Firmware Logic
Scans all button GPIOs with pullups

Reads analog stick values using ADCs

Converts triggers to analog values

Sends state via Bluetooth using BLE HID protocol

🔋 Power Management
Can run from USB 5V or internal LiPo via TP4056

Optional deep sleep/wake via button

Add charge status LED if needed

🖼️ Internal Mounting Tips
Remove the original Xbox controller PCB

Glue or screw the ESP32 board inside cleanly

Reuse original button membranes if possible

Solder to copper pads or add tactile switches

Secure wires and isolate with heatshrink

Close the case and test responsiveness

🎮 Testing
Use this site to verify all inputs:
👉 https://gamepad-tester.com

If analog sticks are off-center or jittery, calibrate ADC readings in code.

🧪 Optional Enhancements
Haptic motor (PWM + MOSFET)

OLED battery/status display

Turbo/fire modes

Dual-device pairing

Macro or profile support

📸 Gallery
Add your before/after photos here to showcase the conversion.

📜 License
Open source, MIT License.
Use it, mod it, break it, improve it. Attribution appreciated.
