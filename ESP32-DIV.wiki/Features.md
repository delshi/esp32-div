# Features of ESP32-DIV

The **ESP32-DIV** is packed with tools for wireless manipulation and analysis, organized into four main menus: Wi-Fi, Bluetooth, 2.4GHz, and Sub-GHz. Each menu offers unique features for testing, jamming, and exploring wireless protocols. Below is a detailed look at what the ESP32-DIV can do.

## 🌐 Wi-Fi Menu
- **Packet Monitor**  
  Visualize live Wi-Fi traffic across all 14 channels with a real-time waterfall graph. Perfect for monitoring network activity and analyzing the wireless environment.

- **Beacon Spammer**  
  Flood the airwaves with fake Wi-Fi access points (beacon frames). Choose to target specific access points with custom names or generate random fake networks to disrupt connections or trick devices.

- **Deauth Detector**  
  Scan for deauthentication attacks and other suspicious activities. Originally designed for deauth detection, it now serves as a general-purpose threat detection tool.

- **Wi-Fi Scanner**  
  List nearby Wi-Fi networks with detailed information (e.g., SSID, channel, signal strength). Ideal for network analysis and security assessments.

- **Wi-Fi Deauthentication Attack**  
  Scan for nearby Wi-Fi networks, select a target access point (AP), and send deauthentication frames to disrupt client connections. Features an intuitive touchscreen interface for network selection and attack management, making it a powerful tool for network security testing and demonstrations.

- **Captive Portal**  
  Create a Wi-Fi access point (AP) that captures user credentials via a login page. Includes a user-friendly touchscreen interface for configuration, credential management, and attack control, ideal for network testing and security demonstrations.

## 📡 Bluetooth Menu
- **BLE Jammer**  
  Flood Bluetooth Low Energy (BLE) advertising channels with noise to disrupt device discovery and connections. Also supports jamming classic Bluetooth channels.

- **BLE Spoofer**  
  Mimic real BLE devices by sending fake advertising packets. Impersonate specific devices to test responses or perform spoofing operations.

- **Sour Apple**  
  Target Apple devices by exploiting BLE features like AirDrop and Continuity. Spoof Apple BLE advertisements to trigger unintended behaviors or potential data leaks.

- **BLE Scanner**  
  Detect nearby BLE devices, including hidden ones, with detailed information on each. Great for analysis and security research.

- **BLE Sniffer**  
  Monitor and display nearby BLE and Classic Bluetooth devices on the TFT screen. Detect suspicious activities like jamming, MAC spoofing, and beacon spoofing, with alerts for potential threats. Shows real-time device information, including MAC addresses and signal strength.

## 📶 2.4GHz Menu
- **2.4GHz Scanner**  
  Scan the entire 2.4GHz spectrum (128 channels) to detect Wi-Fi, Zigbee, and proprietary RF protocols. Useful for identifying non-standard wireless activity.

- **Protokill**  
  Jam wireless protocols on the 2.4GHz band, such as Zigbee and Wi-Fi. Perfect for stress-testing protocols or targeted jamming operations.

## 📻 Sub-GHz Menu
- **Replay Attack**  
  Capture and replay Sub-GHz signals (e.g., door unlock commands) for unauthorized access. Features a real-time waterfall graph and stores signals for later use.

- **Sub-GHz Jammer**  
  Disrupt Sub-GHz devices like garage door openers, remote controls, and IoT sensors. Select specific frequencies or cycle through them automatically.

- **Saved Profiles**  
  Store and manage captured signals from Replay Attacks. Revisit, replay, or delete profiles as needed.

---
*Explore these features with your ESP32-DIV! Check the [Firmware Upload Guide](Firmware-Upload-Guide) to get started.*