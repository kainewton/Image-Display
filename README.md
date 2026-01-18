# OLED Image Display 

This project demonstrates how to display **black & white images (bitmap)** on an **OLED SSD1306 (128x64)** using **Arduino or ESP32**.
The main goal of this project is to learn how OLED displays handle bitmap images and how images must be converted before being shown on a monochrome display.

---

## Overview
OLED displays such as the SSD1306 do not support JPEG or PNG images directly.  
Images must be converted into **1-bit bitmap arrays** before being rendered on the screen.


## Hardware Used
- OLED SSD1306 (I2C, 128x64)
- Arduino UNO / Nano **or** ESP32
- Jumper wires

---

## Wiring (I2C)

### Arduino UNO / Nano
| OLED | Arduino |
|------|---------|
| VCC  | 5V / 3.3V |
| GND  | GND |
| SDA  | A4 |
| SCL  | A5 |

### ESP32
| OLED | ESP32 |
|------|-------|
| VCC  | 3.3V |
| GND  | GND |
| SDA  | GPIO 21 |
| SCL  | GPIO 22 |

---

## Libraries Used
This project uses the following Arduino libraries:
- Adafruit SSD1306
- Adafruit GFX Library

Both libraries can be installed via **Arduino Library Manager**.

---

##  Image Conversion 
OLED SSD1306 only supports **monochrome (1-bit) images**.  
Color images must be converted before use.

###  Online Image Converter (Recommended)
Use the following tool to convert images:
 https://javl.github.io/image2cpp/

**Recommended settings:**
- Resolution: **128 × 64**
- Color mode: **Black & White**
- Output format: **Arduino Code**
- Draw mode: **Horizontal**

After conversion, the generated bitmap can be used in your project.

---

## Alternative Image Conversion Tools
Other tools that can be used:
- **GIMP** – Convert to grayscale and apply threshold
- **Adobe Photoshop** – Grayscale + bitmap mode
- **Python (Pillow + NumPy)** – For advanced image processing

---

##  Notes
- Bitmap resolution must match the OLED resolution
- Common I2C address: `0x3C` (some modules use `0x3D`)
- OLED displays are **black & white only**
- Incorrect bitmap size may result in distorted or blank display

