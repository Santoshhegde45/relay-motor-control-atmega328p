
# 🚀 Relay-Based DC Motor Control using ATmega328P

This project demonstrates how to control a 12V DC motor using a relay, driven by an ATmega328P microcontroller. The system is powered from a 24V DC source, with step-down regulation for motor and logic supplies.

---

## 📌 Features

- ✅ Controls a 12V DC motor via relay
- ✅ Power input: 24V DC
- ✅ 12V regulated supply for the motor (LM2596)
- ✅ 5V regulated supply for ATmega328P and relay logic (7805)
- ✅ Flyback diode and transistor-based relay drive protection
- ✅ External 16MHz crystal oscillator for ATmega328P
- ✅ Clear labeling and modular schematic

---

## 🔧 Schematic Diagram

![Motor Control Schematic](motor_control_schematic.png)

The schematic shows:

- ATmega328P microcontroller with crystal and decoupling setup
- LM2596 buck converter to 12V
- 7805 linear regulator for 5V logic
- Relay driver circuit (2N2222 + diode)
- Common ground and protection

---

## 🧩 Components Used

| Component        | Quantity | Notes                         |
|------------------|----------|-------------------------------|
| ATmega328P-PU     | 1        | Microcontroller (Arduino-based) |
| 16MHz Crystal     | 1        | With 2 × 22pF capacitors       |
| LM2596 Module     | 1        | Step-down from 24V to 12V     |
| 7805 Regulator    | 1        | 5V regulator for logic        |
| 2N2222 NPN Transistor | 1     | For relay driving             |
| 1N4007 Diode      | 2        | Flyback and reverse polarity  |
| 5V Relay Module   | 1        | Controls 12V DC motor         |
| 12V DC Motor      | 1        | Output load                   |
| Capacitors (0.1µF, 100µF) | As needed | Power filtering             |
| Resistors (10kΩ, 330Ω, etc.) | As needed | For pull-ups and biasing   |
| Push Button       | 1        | Manual Reset                  |

---

## 💡 How It Works

1. **Power Supply**
   - 24V DC input is stepped down to:
     - 12V for the motor using LM2596
     - 5V for microcontroller logic using 7805

2. **Control**
   - ATmega328P outputs a signal on a digital pin (e.g., PB0/D8)
   - This signal drives a transistor which activates the relay
   - The relay switches the 12V to the DC motor

3. **Protection**
   - Flyback diode protects the transistor from relay coil back EMF
   - Common ground ensures stable operation

---

## 🛠️ Microcontroller Setup

- 16 MHz crystal oscillator with 2× 22pF capacitors
- 10kΩ pull-up resistor on RESET pin
- Optional UART connection (RX/TX) for programming via USB-TTL
- Code can be uploaded using Arduino as ISP or a programmer

---

## 🧠 Firmware

You can write the firmware using **Arduino IDE**.  
Basic logic:
```cpp
#define RELAY_PIN 8

void setup() {
  pinMode(RELAY_PIN, OUTPUT);
}

void loop() {
  digitalWrite(RELAY_PIN, HIGH); // Turn motor ON
  delay(2000);
  digitalWrite(RELAY_PIN, LOW);  // Turn motor OFF
  delay(2000);
}
```

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

---

## 📷 Preview

You may include:
- Breadboard/PCB photo
- KiCad layout screenshots (if any)
- Simulation waveform (optional)

---

## 🙋‍♂️ Author

**Santosh Hegde**  
Electronics & Communication Engineer | Embedded & PCB Enthusiast

---
