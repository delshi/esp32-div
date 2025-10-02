# Hardware of ESP32-DIV

The **ESP32-DIV** is a compact yet powerful device, built from two main sections: the **Main Board** and the **Shield**. Together, they enable Wi-Fi, BLE, 2.4GHz, and Sub-GHz operations. Below is a breakdown of the hardware components.

## 🛠️ Main Board
- **LF33**: Voltage regulator providing a stable 3.3V supply for reliable operation.
- **TP4056**: Lithium battery charger with built-in protection for safe battery management.
- **CP2102**: USB-to-serial converter for flashing firmware and serial communication.
- **PCF8574**: I/O expander to manage multiple button inputs for user interaction.
- **SD Card Slot**: Stores captured signals, logs, and configurations.
- **ESP32-U (16MB)**: The core microcontroller with Wi-Fi and BLE capabilities, featuring 16MB flash memory.
- **Antenna Connector**: Supports external antennas for enhanced signal range.
- **ILI9341 TFT Display**: 2.8-inch screen for user interface and real-time data visualization.
- **Push Buttons**: For navigating menus and interacting with the device.

![image](https://github.com/user-attachments/assets/6507767e-9595-4235-a159-8cae16e65973)


## 🛡️ Shield
- **3 x NRF24 Modules**: Enable 2.4GHz operations, including scanning, jamming, and protocol analysis.
- **CC1101 Module**: Sub-GHz transceiver for replay attacks, jamming, and signal capture.

![image](https://github.com/user-attachments/assets/f8e3c49c-a6a0-4721-996d-f52f6dc5ffec)


---
*For connection details, see the [Schematics](Schematics) page. Get your device running with the [Firmware Upload Guide](Firmware-Upload-Guide).*