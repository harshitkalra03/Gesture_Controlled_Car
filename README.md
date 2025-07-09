# 🤖 Gesture Controlled Car

![Project Stage](https://img.shields.io/badge/status-Prototype-orange)
![License](https://img.shields.io/badge/license-MIT-blue)
![Platform](https://img.shields.io/badge/platform-Arduino%20UNO%20%7C%20Nano-blue)
![Power](https://img.shields.io/badge/power-LiPo%202S%20%2B%2018650-red)
![Communication](https://img.shields.io/badge/communication-NRF24L01-yellowgreen)
![Sensor](https://img.shields.io/badge/sensor-MPU6050-lightgrey)

![Last Commit](https://img.shields.io/github/last-commit/harshitkalra03/Gesture_Controlled_Car)
![Repo Stars](https://img.shields.io/github/stars/harshitkalra03/Gesture_Controlled_Car?style=social)
![Repo Forks](https://img.shields.io/github/forks/harshitkalra03/Gesture_Controlled_Car?style=social)

---

A 4-wheeled differential drive robot controlled wirelessly via **hand gestures**, using an **MPU6050** sensor and **NRF24L01** modules. This project demonstrates RF-based communication, motion control, and embedded system integration in robotics.

---

## 📅 Project Timeline

| Phase                 | Date             |
|-----------------------|------------------|
| Idea Development      | December 2024    |
| Research & Trials     | Jan–June 2025    |
| Development Started   | July 6, 2025     |

---

## 🎯 Motivation

Driven by a strong curiosity to:
- Learn **RF communication** using NRF24L01
- Understand **gesture control mechanisms** through MPU6050
- Build a modular and functional **robotics system from scratch**

---

## ❗ Pre-Development Challenges (Before July 2025)

> ⚠️ While exploring the feasibility of the project between **Jan–June 2025**, multiple issues delayed implementation:

- Unstable and inconsistent NRF24L01 communication
- Despite research and code trials, communication couldn’t be stabilized
- Suspected causes:
  - Power supply noise
  - Lack of proper decoupling
  - Weak or inconsistent solder connections
  - Inconsistent 3.3V power from Arduino boards
  - Possibility of faulty or damaged NRF modules

> These challenges **delayed the realisation** phase to **July 2025**.

---

## ✅ Work Summary (July 6–9, 2025)

### 🧱 1. Chassis Fabrication
- Used a 4WD robot chassis kit:
  - 2 acrylic base plates
  - 4 BO motors with wheels
  - M3x5 screws, M3x30mm brass standoffs
  - Binding wire for extra mechanical strength

---

### ⚙️ 2. Receiver Circuit Assembly 
> *(add circuit diagram)*
- Components used:
  - **Arduino UNO**
  - **NRF24L01 (RX)**
  - **L298N Motor Driver**
  - **4 BO motors** connected through the driver
- Power:
  - Motors powered by a **2S 2800mAh LiPo battery**
  - Controller and NRF powered using a **18650 2200mAh Li-ion cell**
- Safety and modularity:
  - **XT60 connectors** for clean battery detachment
  - **SPST switch** for isolating power
  - **Thicker gauge wires** to prevent wire overheating under motor load

---

### 📡 3. Transmitter Circuit (Perfboard)
> *(add circuit diagram)*
- Designed a compact custom transmitter using:
  - **Arduino Nano**
  - **MPU6050** (for motion/gesture input)
  - **NRF24L01 (TX)**
  - **Green LED** for status indication
  - **Push Button** to control or reset communication
  - **220Ω resistors** for LED and signal protection
  - **2-pin JST connector** for battery input (18650 cell)

---

### ⚡ 4. Power Stabilization
- **Decoupling capacitor (10µF–50µF)** added across NRF24L01 VCC–GND to reduce power noise
- ➕ *Insight:*  
  RF modules like NRF24L01 are extremely sensitive to power fluctuations. Even brief dips or noise spikes can cause packet drops or full loss of communication.  
  Adding a **10μF–100μF capacitor** helps buffer the current demand during transmissions and keeps communication stable.

---

### 🔧 5. Soldering Challenges
- First attempt at a perfboard-based robotics circuit
- Key issues faced:
  - Soldering **female berg strips** for NRF module (loose or unstable initially)
  - General layout and spacing issues
- Required **rework** and **component re-alignment** to achieve consistent performance

---

## 🧰 Components Used

| Component             | Quantity | Notes                                      |
|------------------------|----------|--------------------------------------------|
| Arduino UNO            | 1        | Receiver side                              |
| Arduino Nano           | 1        | Transmitter side                           |
| NRF24L01               | 2        | Wireless communication (TX/RX)             |
| MPU6050                | 1        | Motion sensor for gesture control          |
| L298N Motor Driver     | 1        | Controls the 4 BO motors                   |
| BO Motors              | 4        | Differential drive setup                   |
| Wheels                 | 4        | Coupled to motors                          |
| 2S 2800mAh LiPo        | 1        | Power for motor driver                     |
| 18650 Li-ion Cells     | 2        | One for TX circuit, one for RX circuit     |
| 220Ω Resistors         | 2        | Used for LED and pull-up where needed      |
| XT60 Connectors        | 1 pair   | Power modularity                           |
| Capacitors (10µF–50µF) | 1–2      | NRF power filtering                        |
| Standoffs M3x30mm      | 4        | Mounting chassis plates                    |
| SPST Switch            | 1        | Receiver side circuit                      |
| 2-Pin Connector        | 1        | Power connector for TX circuit             |
| Green LED              | 1        | Visual status indicator                    |
| Push Button            | 1        | Mode toggle/reset on transmitter           |
| Acrylic Sheets         | ~2       | Used in chassis and electronics mounting   |

---

## 📷 Media

> *(To be added in future commits)*

- 🖼️ Photos:
  - Chassis fabrication
  - Wiring layout
  - Perfboard soldering
- 🎥 Videos:
  - Gesture control demo
  - Initial testing with serial feedback
- 📑 Debug Logs:
  - NRF24L01 connection errors (before July 2025)
  - Power fluctuation capture, if available

---

## 🚀 Next Steps

- [ ] Map MPU6050 tilt gestures to movement directions (forward, backward, left, right)
- [ ] Add logic to handle communication timeout or module failure
- [ ] Add basic feedback from car (e.g., ACK or status LED)
- [ ] Perform field test for range and latency
- [ ] Create wiring diagrams & share open-source code

---

## 💡 Learnings

- Importance of **separate and stable power lines** for logic vs motor domains
- Proper **decoupling capacitors** are crucial for RF modules
- Perfboard soldering requires planning and precision
- Modular connections (switches, JSTs, XT60s) save time and reduce errors
- Real-time debugging and logs help isolate communication failures

---

## 👨‍💻 Author

**Harshit Kalra**  
📍 *IIT Ropar – Robotics Club*  
🛠️ Passionate about embedded systems, robotics, and learning through real-world projects.  
🗂️ This project was initiated as a hands-on experiment and learning journey into wireless gesture-based control.
