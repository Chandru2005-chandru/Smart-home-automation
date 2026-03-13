# 🏠⚡ Smart Home Automation (Arduino)

A simple **Smart Home Automation** project using **Arduino** + sensors to detect **gas/smoke**, **flame**, **rain**, and **light (LDR)**, showing status on a **16x2 I2C LCD** and triggering **alerts (buzzer + LED)**.

---

## ✨ Features
- 🔥 **Flame detection** (Fire alert)
- 💨 **Gas/Smoke detection** using MQ2 (Analog + Digital)
- 🌧️ **Rain detection** (Warning)
- 🌙💡 **Auto light control** using LDR (Light/Dark)
- 📟 **16x2 I2C LCD display** for live status
- 🚨 **Buzzer + Alert LED** for emergency conditions
- 🖥️ Serial Monitor logging at **9600 baud**

---

## 🧰 Components Required
- ✅ Arduino UNO / Nano (or compatible)
- ✅ MQ2 Gas/Smoke sensor
- ✅ LDR sensor module
- ✅ Flame sensor module
- ✅ Rain sensor module
- ✅ 16x2 I2C LCD (address usually `0x27` or `0x3F`)
- ✅ Buzzer
- ✅ LEDs + resistors + jumper wires + breadboard

---

## 🔌 Pin Connections (As in code)

### Sensors
- MQ2 **Analog (AO)** → `A0`
- MQ2 **Digital (DO)** → `D8`
- LDR → `A1`
- Flame sensor → `D2`
- Rain sensor → `D3`

### Outputs
- Buzzer → `D4`
- Light LED → `D5`
- Alert LED → `D6`

---

## 📚 Libraries Used
- `Wire.h`
- `LiquidCrystal_I2C.h` ✅ (Install from Arduino Library Manager)

---

## 🚀 How to Upload & Run

1) Open the Arduino IDE  
2) Open: `SMART_HOME_AUTOMATION.ino`  
3) Install library: **LiquidCrystal_I2C**
4) Select your board: **Tools → Board → Arduino Uno** (or your board)
5) Select port: **Tools → Port**
6) Click **Upload** ✅  
7) Open **Serial Monitor** (set baud rate to **9600**)  

---

## 🖥️ What You’ll See
📟 LCD shows:
- Smoke analog value (`Smoke: <value>`)
- Light status (`Light` / `Dark`)
- Status message:
  - 🔥 `FLAME ALERT!`
  - 💨 `Gas/Smoke Detected`
  - 🌧️ `Rain Warning`
  - ✅ `All Normal`

---

## ⚙️ Thresholds (Current)
- Smoke warning on LCD when `smokeValue > 400`
- Alert buzzer + alert LED when:
  - `gasDetected == true` OR
  - `smokeValue > 200` OR
  - `flameDetected == true`
- LDR light/dark threshold: `500`

> You can tune these values depending on your sensors.

---

## 🛡️ Safety Note
This is a **DIY demo project**. Do not use it as the only safety system for fire/gas detection in real homes.

---

## 📄 License
Add a license if you plan to share or reuse this project (MIT is common).