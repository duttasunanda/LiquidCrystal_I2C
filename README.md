# 📟 LiquidCrystal_I2C for Arduino

This repository contains the **LiquidCrystal_I2C** library used to control **16x2 or 20x4 I2C LCD Displays** with Arduino boards. It allows you to easily print text, control the cursor, and manage the display using just **two wires (SDA, SCL)** instead of 6+.

---

## 📦 Features

✅ Supports 16x2 and 20x4 I2C LCD Displays  
✅ Works with all Arduino-compatible boards  
✅ Simple and clean API (easy to use)  
✅ Controls backlight, cursor, and scroll text  
✅ Ideal for projects with limited pins (uses I2C)

---

## 🔌 I2C Wiring Diagram (for Arduino UNO)

| LCD Pin | Arduino Pin |
|---------|-------------|
| SDA     | A4          |
| SCL     | A5          |
| VCC     | 5V          |
| GND     | GND         |

> ⚠️ Note: The I2C address is usually `0x27` or `0x3F`. Use an [I2C Scanner](https://playground.arduino.cc/Main/I2cScanner/) sketch to find the correct address for your LCD.

---

## 📥 Installation (Easy Steps)

### 🔹 Method 1: Install from ZIP (Recommended)

1. Click the green **`Code`** button → Download ZIP  
2. Open **Arduino IDE**  
3. Go to **Sketch > Include Library > Add .ZIP Library**  
4. Select the downloaded ZIP file  
5. Done! ✅

### 🔹 Method 2: Manual Installation

1. Download the ZIP  
2. Extract the folder  
3. Rename the folder to `LiquidCrystal_I2C` (if needed)  
4. Copy it to your Arduino libraries folder:
   - Windows: `Documents/Arduino/libraries/`
   - Linux: `~/Arduino/libraries/`
   - macOS: `~/Documents/Arduino/libraries/`

---

## 🧪 Sample Code

```cpp
#include <Wire.h>
#include <LiquidCrystal_I2C.h>

LiquidCrystal_I2C lcd(0x27, 16, 2); // Address 0x27, 16 chars, 2 lines

void setup() {
  lcd.init();            // Initialize LCD
  lcd.backlight();       // Turn on backlight
  lcd.setCursor(0, 0);
  lcd.print("Hello, World!");
  lcd.setCursor(0, 1);
  lcd.print("I2C LCD Ready");
}

void loop() {
  // Your code here
}
````

---

## 🛠️ Troubleshooting

| Issue                 | Solution                                   |
| --------------------- | ------------------------------------------ |
| Nothing on LCD        | Check I2C address and wiring (use scanner) |
| Backlight on, no text | Call `lcd.init()` before `lcd.print()`     |
| Garbage characters    | Confirm your LCD is 16x2 or 20x4           |

---

## 💡 Pro Tip

Use `lcd.setCursor(col, row)` to place text anywhere.
You can scroll, clear screen, blink cursor, and more!

```cpp
lcd.scrollDisplayLeft();
lcd.clear();
lcd.noBacklight();
lcd.cursor();
lcd.blink();
```

---

## 🤝 Credits

* Forked and maintained by [**Sunanda Dutta**](https://github.com/duttasunanda)
* Based on original LiquidCrystal\_I2C by Frank de Brabander and open-source contributors

---

## 📜 License

This library is open-source and distributed under the **MIT License**.
Feel free to use, modify, and share!

---

⭐ **If you found this library useful, please star the repo and share it with others!**

