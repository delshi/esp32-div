# Schematics of ESP32-DIV

The **ESP32-DIV** integrates multiple components with the ESP32 microcontroller for its wireless capabilities. Below are the key connections. Refer to the [ESP32-DIV GitHub repository](https://github.com/your-repo-link/esp32-div) for detailed schematic files.

## ⚙️ TFT Display + ESP32
![image](https://github.com/user-attachments/assets/66e5231e-aa6c-468a-8240-58b20c0e1869)

- **ILI9341 TFT Display**: Connected to the ESP32 for the user interface.
- **LED Backlight Control**: Managed via a transistor switch (Q3, 8050) with a 1kΩ resistor (R26) at the base. Supports PWM for brightness adjustment if implemented.

## 🖥️ XPT2046 + ESP32
![image](https://github.com/user-attachments/assets/54893eb8-e3a1-433a-956e-48113d2d76e1)

- **XPT2046**: Touch controller for the TFT display, interfaced with the ESP32 for touch input.

## 📡 NRF24 Modules - Connections to ESP32
![image](https://github.com/user-attachments/assets/34f58d4e-a3f3-4f6e-aaeb-c8ca8a012415)

- **3 x NRF24 Modules**: Connected to the ESP32 for 2.4GHz operations (scanning, jamming, etc.). Each module uses SPI pins for communication.

## 📻 CC1101 Sub-GHz Transceiver - Connections to ESP32
![image](https://github.com/user-attachments/assets/383f6da3-4117-4f3c-8c0f-c2b117bcdd22)

- **CC1101 Module**: Connected to the ESP32 via SPI for Sub-GHz signal capture, replay, and jamming.

## 💾 SD Card - Connections to ESP32
![image](https://github.com/user-attachments/assets/426ed6a4-c4c7-4e62-9fd4-e20b48e93400)

- **SD Card Slot**: Interfaced with the ESP32 via SPI for storing signals, logs, and firmware files.

**Note**: Exact pin assignments (e.g., SPI MOSI, MISO, SCK) depend on the firmware configuration. Check the repository’s schematic files or source code for precise mappings.

---
*Build or troubleshoot your ESP32-DIV with these connections. See the [Hardware](Hardware) page for component details or the [Firmware Upload Guide](Firmware-Upload-Guide) for setup.*