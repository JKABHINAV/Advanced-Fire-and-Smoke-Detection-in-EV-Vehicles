# Advanced-Fire-and-Smoke-Detection-in-EV-Vehicles

An Arduino-based safety system designed to monitor Electric Vehicle (EV) battery compartments and cabins. In the event of a fire or thermal runaway detection, the system triggers an immediate local alarm and sends remote alerts via SMS and Phone Calls using the SIM800L GSM module.

## 🚀 Key Features
* **Dual-Alert System:** Sends automated SMS and makes emergency calls to up to 3 pre-configured numbers.
* **Real-time Monitoring:** Continuous flame sensor polling with optimized logic for vehicle environments.
* **Audio-Visual Alarm:** High-decibel buzzer for immediate on-site warning.
* **Robust Logic:** Optimized to prevent "looping" alerts during a single fire event.

## 🛠️ Hardware Components
* **Microcontroller:** Arduino Nano or Uno
* **GSM Module:** SIM800L (Requires a stable 3.7V-4.2V / 2A power source)
* **Sensor:** IR Flame Sensor (Digital Output)
* **Alert:** 5V Active Buzzer
* **Power:** 12V to 5V/4V Buck Converter (to tap into EV auxiliary power safely)

## 📋 Wiring Diagram & Pin Mapping



| Component | Arduino Pin | Notes |
| :--- | :--- | :--- |
| **Flame Sensor (D0)** | D2 | Triggers LOW on fire detection |
| **Buzzer (+)** | D5 | 5V Active Buzzer |
| **SIM800L (TX)** | D4 | SoftwareSerial RX |
| **SIM800L (RX)** | D3 | SoftwareSerial TX |
| **Common Ground** | GND | All grounds MUST be connected |

## 💻 Installation & Setup

1. **Clone the Repo:** Download the code to your local machine.
2. **Configuration:** - Open the `.ino` file in the Arduino IDE.
   - Replace the placeholder numbers in `PHONE_1`, `PHONE_2`, etc., with your emergency contact numbers in international format (e.g., `+911234567890`).
3. **Power Note:** Do not power the SIM800L directly from the Arduino 5V pin. Use an external battery or a buck converter capable of 2A bursts.
4. **Upload:** Connect your Arduino via USB and click **Upload**.

## ⚠️ Important Notes for EV Implementation
* **Thermal Runaway:** While this code uses a flame sensor, adding a thermistor (temperature sensor) is recommended for early detection of battery overheating.
* **Placement:** Mount the flame sensor inside the battery housing or near high-voltage terminals. Ensure it is shielded from direct sunlight to avoid false IR triggers.
* **Network:** Ensure the SIM card used has the PIN lock disabled and has sufficient balance for SMS and Calls.

## 📄 License
This project is open-source. Feel free to modify and adapt it for your specific vehicle safety needs.

---
*Developed for EV Safety Research & Development.*
