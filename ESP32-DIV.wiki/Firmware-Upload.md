# Firmware Upload Guide for ESP32-DIV

The **ESP32-DIV** requires firmware or code to unlock its wireless capabilities. This guide covers three methods to upload firmware: **OTA/SD Card**, **Flash Download Tool**, and **Arduino IDE**. These methods suit both beginners and advanced users.

⚠️ **Note**: Always download firmware and sketches from the [ESP32-DIV GitHub repository](https://github.com/cifertech/ESP32-DIV).

## Method 1: Update Firmware via OTA or SD Card
If your ESP32-DIV is running its main firmware, use the built-in update feature via Over-The-Air (OTA) or SD card. This method is ideal for quick, computer-free updates using the TFT display.

### What You’ll Need
- Working ESP32-DIV with main firmware and functional TFT display.
- MicroSD card (FAT32 formatted) for SD card updates.
- `.bin` firmware file from the repository.
- Wi-Fi credentials for OTA updates.
- Computer or phone to host the firmware file for OTA.

### Steps for OTA Update
1. **Get the Firmware File**:
   - Download the latest `.bin` file from the [ESP32-DIV GitHub repository](https://github.com/cifertech/ESP32-DIV).
   - Host it on a server or computer and note the URL (e.g., `http://192.168.1.100/firmware.bin`).

2. **Connect to Wi-Fi**:
   - Power on the ESP32-DIV. Go to **Wi-Fi Settings** on the TFT display.
   - Select your network, enter the password using the on-screen keyboard, and connect.

3. **Run the OTA Update**:
   - Navigate to **Firmware Update** menu, select **OTA Update**, and enter the firmware URL.
   - Press **Update** to download and flash. The device reboots when done.

4. **Check the Update**:
   - Verify the new firmware version on the TFT display or Serial Monitor (115200 baud).
   - If it fails, check the URL and Wi-Fi stability, then retry.

### Steps for SD Card Update
1. **Prepare the SD Card**:
   - Format a microSD card to FAT32.
   - Download the latest `.bin` file from the [ESP32-DIV GitHub repository](https://github.com/cifertech/ESP32-DIV) and rename it to `firmware.bin`.
   - Place `firmware.bin` in the SD card’s root directory and eject safely.

2. **Insert the SD Card**:
   - Power off the ESP32-DIV and insert the SD card.

3. **Run the SD Card Update**:
   - Power on, go to **Firmware Update**, and select **SD Card Update**.
   - Select `firmware.bin` and press **Update**. The device reboots after flashing.

4. **Check the Update**:
   - Confirm the firmware version on the TFT display or Serial Monitor.
   - The file may be renamed (e.g., `firmware.bak`). Remove or reformat the SD card for future use.

### Tips
- **OTA**: Ensure a strong Wi-Fi signal and keep the host online.
- **SD Card**: Use a reliable microSD card. Power off before inserting/removing.
- **Troubleshooting**: Verify the `.bin` file, ensure FAT32 format, or check Serial Monitor for errors.

## Method 2: Flash a .bin File with Flash Download Tool
Use the Espressif Flash Download Tool to upload firmware via USB. This is great for initial setups or restoring a non-working device.

### What You’ll Need
- ESP32-DIV with USB-C/micro-USB port.
- Computer (Windows, macOS, Linux).
- USB cable.
- `.bin` firmware file from the [ESP32-DIV GitHub repository](https://github.com/cifertech/ESP32-DIV/tree/main/Pre-compiled%20Bin).
- `.partitions` firmware file from the [ESP32-DIV GitHub repository](https://github.com/cifertech/ESP32-DIV/tree/main/Flash%20File).
- [Espressif Flash Download Tool](https://www.espressif.com/en/support/download/other-tools).

### Steps
1. **Prepare the Firmware File**:
   - Download the `.bin` file from the repository.
   - Download the `.partitions` file from the repository.

2. **Install the Flash Download Tool**:
   - Download and install the tool. Run as administrator on Windows.

3. **Connect the ESP32-DIV**:
   - Connect via USB and enter **Download Mode**:
     - Hold **BOOT** button, press **RESET** briefly, release both.
   - Select the correct COM port in the tool.

4. **Configure Flash Settings**:
   - Select **ESP32** chip type and **Developer Mode** or **Download Mode**.
   - Load the `.bin` file, set flash offset to `0x10000`.
   - Load the `.partitions` file, set flash offset to `0x8000`.
   - Set **SPI Speed** to 40 MHz, **SPI Mode** to DIO.
   - Check the `.bin` and `.partitions` file boxes.

5. **Flash the Firmware**:
   - Click **START**. Wait for “FINISH” or “Download Complete” (1-2 minutes).

6. **Reset and Verify**:
   - Power cycle the ESP32-DIV. Check the TFT display or Serial Monitor for the new firmware version.
   - If it fails, verify COM port, offset, or Download Mode.

### Tips
- Install USB-to-serial drivers (e.g., CP2102, CH340) if needed.
- Verify the `.bin` file matches your hardware.
- Try a different USB cable/port or lower SPI Speed (20 MHz) if flashing fails.

## Method 3: Upload Sketch via Arduino IDE
Compile and upload the ESP32-DIV sketch for customization. This method requires specific setup for the 4MB or 16MB ESP32 versions.

### What You’ll Need
- ESP32-DIV with USB-C/micro-USB port.
- Computer with [Arduino IDE](https://www.arduino.cc/en/software) (2.x or 1.8.x).
- USB cable.
- ESP32-DIV sketch, [library ZIP](https://github.com/cifertech/ESP32-DIV/tree/main/Libraries), and [platform.txt](https://github.com/cifertech/ESP32-DIV/tree/main/Flash%20File) from the [ESP32-DIV GitHub repository](https://github.com/cifertech/ESP32-DIV).

### Steps
1. **Install Arduino IDE and ESP32 Board Package**:
   - Install the Arduino IDE.
   - Go to **Tools > Board > Boards Manager**, search “esp32,” and install **esp32 by Espressif Systems** (version 2.0.10).

2. **Replace platform.txt**:
   - Download `platform.txt` from the repository.
   - Replace the file in:
     - Windows: `C:\Users\<YOUR_USERNAME>\AppData\Local\Arduino15\packages\esp32\hardware\esp32\2.0.10`
     - macOS: `~/Library/Arduino15/packages/esp32/hardware/esp32\2.0.10`
     - Linux: `~/.arduino15/packages/esp32/hardware/esp32\2.0.10`
   - Back up the original.

3. **Replace Library Files**:
   - Download the library ZIP from the repository and unzip it.
   - Replace existing library folders in:
     - Windows: `C:\Users\<YOUR_USERNAME>\Documents\Arduino\libraries`
     - macOS: `~/Documents/Arduino/libraries`
     - Linux: `~/Arduino/libraries`
   - Restart the Arduino IDE.

4. **Download and Open Sketch**:
   - Download the `.ino` sketch from the repository and open it in the IDE.

5. **Configure Arduino IDE Settings**:
   - Connect the ESP32-DIV via USB.
   - Select **Tools > Board > ESP32 Dev Module** and the correct **Port**.
   - Configure based on flash size:
     - **4MB ESP32**:
       - **Partition Scheme**: Rainmaker, Huge APP, or Minimal SPIFFS.
       - **Flash Size**: 4MB.
     - **16MB ESP32**:
       - **Partition Scheme**: 16MB Flash (3MB APP/9.9MB FATFS).
       - **Flash Size**: 16MB.
   - Optional: Set **Upload Speed** to 921600, **CPU Frequency** to 240 MHz.

6. **Compile and Upload**:
   - Click **Verify** to compile. Fix any errors.
   - Click **Upload**. Enter **Download Mode** if prompted (hold **BOOT**, press **RESET**, release both).
   - Wait for “Done uploading.”

7. **Verify Upload**:
   - Check the TFT display or Serial Monitor (115200 baud).
   - If it fails, verify settings, port, or Download Mode.

### Tips
- Ensure libraries match the ZIP file to avoid conflicts.
- Install USB-to-serial drivers if the port isn’t detected.
- Lower upload speed to 115200 or try another cable/port if needed.

---
*Your ESP32-DIV is ready! Explore its tools on the [Features](Features) page.*