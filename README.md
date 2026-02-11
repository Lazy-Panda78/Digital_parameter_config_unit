# Digital Parameter Config Unit

A PlatformIO-based Arduino project for controlling and displaying parameters on an OLED display using the Arduino UNO R4 WiFi board.

## Table of Contents
- [IDE Information](#ide-information)
- [Code](#code)
- [Libraries](#libraries)
- [Dependencies](#dependencies)
- [Hardware Components](#hardware-components)
- [Software Requirements](#software-requirements)
- [Hardware Requirements](#hardware-requirements)
- [Author Information](#author-information)

---

## IDE Information

### IDE Used
**CLion** - A cross-platform IDE for C and C++ by JetBrains

### IDE Version
- CLion (latest compatible version with PlatformIO plugin)
- PlatformIO IDE integration plugin enabled

### Platform Details
- **Platform**: PlatformIO
- **Framework**: Arduino
- **Board**: Arduino UNO R4 WiFi (Renesas RA platform)

---

## Code

The main code is located in `src/main.cpp` and initializes an OLED display to show a simple greeting message.

### Main Features:
- Initializes serial communication at 9600 baud
- Configures and initializes SSD1306 OLED display (128x64)
- Displays custom text on the OLED screen
- Error handling for OLED initialization

### Code Structure:
```cpp
#include <Arduino.h>
#include <Wire.h>
#include <Adafruit_GFX.h>
#include <Adafruit_SSD1306.h>

#define SCREEN_WIDTH 128
#define SCREEN_HEIGHT 64
#define OLED_ADDR 0x3C

Adafruit_SSD1306 display(SCREEN_WIDTH, SCREEN_HEIGHT, &Wire, -1);

void setup() {
    // Serial communication initialization
    // OLED display initialization
    // Display text configuration
}

void loop() {
    // Main program loop
}
```

---

## Libraries

The project uses the following Arduino libraries:

### 1. **Adafruit GFX Library** (v1.12.4)
   - Core graphics library for displays
   - Provides basic drawing functions (lines, rectangles, circles, text, etc.)
   - Repository: https://github.com/adafruit/Adafruit-GFX-Library

### 2. **Adafruit SSD1306** (v2.5.16)
   - Driver library for SSD1306 OLED displays
   - Supports I2C and SPI communication
   - Repository: https://github.com/adafruit/Adafruit_SSD1306

### 3. **Arduino Core Libraries**
   - `Arduino.h` - Main Arduino framework
   - `Wire.h` - I2C communication library

---

## Dependencies

### Library Dependencies
```ini
lib_deps = 
    adafruit/Adafruit GFX Library@^1.12.4
    adafruit/Adafruit SSD1306@^2.5.16
```

### Platform Dependencies
- **Platform**: renesas-ra
- **Framework**: Arduino
- **Monitor Speed**: 9600 baud
- **Upload Port**: COM14
- **Monitor Port**: COM14

---

## Hardware Components

### Components Used with OLED Display

1. **Arduino UNO R4 WiFi**
   - Main microcontroller board
   - Based on Renesas RA4M1 (Arm Cortex-M4)
   - 5V operating voltage
   - Built-in WiFi capability

2. **SSD1306 OLED Display (128x64)**
   - Screen Size: 0.96" (typical)
   - Resolution: 128x64 pixels
   - Communication Protocol: I2C
   - I2C Address: 0x3C
   - Operating Voltage: 3.3V - 5V
   - Color: Monochrome (typically white or blue)

3. **I2C Connections**
   - SDA (Serial Data Line)
   - SCL (Serial Clock Line)
   - VCC (Power Supply)
   - GND (Ground)

### Wiring Diagram

```
Arduino UNO R4 WiFi    →    SSD1306 OLED Display
─────────────────────────────────────────────────
    SDA (A4)           →         SDA
    SCL (A5)           →         SCL
    5V                 →         VCC
    GND                →         GND
```

---

## Software Requirements

### Required Software
1. **CLion IDE**
   - Download from: https://www.jetbrains.com/clion/

2. **PlatformIO Plugin**
   - Install via CLion Plugin Marketplace
   - Provides embedded development support

3. **PlatformIO Core**
   - Automatically installed with PlatformIO plugin
   - Manages libraries and platforms

4. **USB Drivers**
   - Arduino UNO R4 WiFi drivers (typically auto-installed)
   - CH340/CP2102 drivers if needed

### Operating System
- Windows, macOS, or Linux
- This project was developed on Windows

---

## Hardware Requirements

### Essential Hardware
1. **Arduino UNO R4 WiFi Board** × 1
2. **SSD1306 OLED Display (128×64, I2C)** × 1
3. **USB Type-C Cable** × 1 (for programming and power)
4. **Jumper Wires** × 4 (for I2C connections)
5. **Breadboard** × 1 (optional, for prototyping)

### Optional Hardware
- External power supply (if not using USB power)
- Additional sensors or input devices for parameter configuration
- Push buttons for user input
- Resistors and capacitors as needed

---

## Author Information

**Author**: Yash

**Project**: Digital Parameter Config Unit

**Academic Context**: 
- Semester: IV
- Course/Lab: Embedded Systems / Microcontroller Programming

**Contact Information**:
- yash.upadhyay_cs.aiml24@gla.ac.in
- https://github.com/Lazy-Panda78

**Date**: February 2026

---

## Getting Started

### Installation Steps

1. **Clone or download this repository**
   ```bash
   git clone <repository-url>
   cd Digital_parameter_config_unit
   ```

2. **Open in CLion**
   - Open CLion IDE
   - Select "Open" and navigate to the project directory
   - CLion will detect the PlatformIO project

3. **Build the project**
   - PlatformIO will automatically download required libraries
   - Click on "Build" or use PlatformIO toolbar

4. **Upload to Arduino**
   - Connect Arduino UNO R4 WiFi via USB
   - Ensure correct COM port is configured in `platformio.ini`
   - Click "Upload" or use PlatformIO upload command

5. **Monitor Serial Output**
   - Open Serial Monitor at 9600 baud
   - Check for "OLED not found" error messages

---

## Troubleshooting

### Common Issues

1. **OLED not found**
   - Check I2C connections (SDA, SCL, VCC, GND)
   - Verify I2C address (0x3C is common, some use 0x3D)
   - Test I2C scanner sketch to detect address

2. **Upload Failed**
   - Check USB cable connection
   - Verify correct COM port in `platformio.ini`
   - Install Arduino UNO R4 WiFi drivers

3. **Display not showing text**
   - Ensure `display.display()` is called after drawing
   - Check contrast settings
   - Verify power supply to OLED

---

## Future Enhancements

- [ ] Add parameter configuration interface
- [ ] Implement button controls for navigation
- [ ] Store parameters in EEPROM
- [ ] Add WiFi connectivity features
- [ ] Create menu system for display

---

## License

[Add your license here - e.g., MIT, GPL, etc.]

---

## Acknowledgments

- Adafruit Industries for the excellent display libraries
- Arduino community for extensive documentation
- PlatformIO for the development platform

---

**Last Updated**: February 11, 2026

