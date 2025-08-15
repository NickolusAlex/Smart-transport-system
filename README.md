# GPS & GSM Based Student Location Tracker

## 📌 Overview
This project is a GPS and GSM-based location tracking system built using Arduino.  
It fetches GPS coordinates via a GPS module, processes the data with the **TinyGPS** library, and sends location updates as SMS messages using a GSM module.

Originally developed 6 years ago, this project demonstrates a simple IoT tracking solution suitable for applications like:
- Student location monitoring
- Vehicle tracking
- Asset security systems

---

## 🛠 Hardware Requirements
- Arduino Uno / Nano *(tested on Uno)*
- GPS Module *(e.g., NEO-6M GPS)*
- GSM Module *(e.g., SIM900 or SIM800L)*
- Jumper wires
- Power supply *(USB or external)*

---

## 📦 Software Requirements
- Arduino IDE
- **TinyGPS** library for parsing GPS data
- **SoftwareSerial** library *(built-in with Arduino IDE)*

---

## ⚙ How It Works
1. **GPS Module** sends location data to Arduino via serial.
2. Arduino uses **TinyGPS** to extract:
   - Latitude
   - Longitude
   - Altitude
   - Date & Time
   - Speed & Course
3. The system formats this data and:
   - Displays it in the Serial Monitor
   - Sends it via **GSM SMS** to a predefined phone number

---

## 📂 Project Files
- **gps_gsm_tracker.ino** → Main Arduino code that:
  - Reads GPS data
  - Formats location output
  - Sends SMS via GSM module
- **gps_serial_logger.ino** → Debugging script to:
  - Read GPS data
  - Print detailed GPS stats to Serial Monitor

---

## 🔌 Pin Connections

| Component      | Arduino Pin | Notes |
|----------------|------------|-------|
| GPS Module TX  | D4         | Connected via SoftwareSerial |
| GPS Module RX  | D3         | Connected via SoftwareSerial |
| GSM Module TX  | D7         | Change if needed |
| GSM Module RX  | D8         | Change if needed |
| Power          | 5V & GND   | Common ground required |

---

## 📜 Example SMS Output
```
Student in
12.9716
77.5946
```

Where:
- **12.9716** → Latitude  
- **77.5946** → Longitude

---

## 🚀 How to Upload & Run
1. Connect your Arduino to the PC.
2. Open the `.ino` file in **Arduino IDE**.
3. Install the **TinyGPS** library via  
   *Sketch → Include Library → Manage Libraries*.
4. Change the phone number inside the code:
   ```cpp
   Serial.print("\"+91xxxxxxxxxx\"");
   ```
5. Select the correct board & port.
6. Upload the code.
7. Open Serial Monitor to see GPS logs.

---

## ⚠️ Notes
- The GPS module may take **30–60 seconds** to get the first fix.
- Ensure GSM SIM card has sufficient balance for SMS.
- Replace `+91xxxxxxxxxx` with your target phone number.

---

