# 🔥 Evil Twin WiFi Captive Portal - ESP8266

<p align="center">
  <img src="https://img.shields.io/badge/Platform-ESP8266-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/Language-C++-brightgreen?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-MIT-yellow?style=flat-square"/>
</p>

## ⚠️ Educational Purpose Only

This project demonstrates how to create a Wi-Fi **Evil Twin** access point on an ESP8266, imitating legitimate networks and serving a captive portal. It's intended **solely for educational and research purposes.**

> ⚠️ **Do not use this code for malicious activity. Unauthorized network interference is illegal in many jurisdictions.**

---

## ✨ Features

* 🔍 **WiFi Network Scanner** — Displays nearby SSIDs with signal strength, channel, and BSSID.
* 📶 **Captive Portal** — Automatically intercepts user connections across devices (Android, iOS, Windows, Linux).
* 🎯 **Evil Twin Mode** — Creates a fake AP with a targeted SSID and BSSID.
* 💣 **Deauthentication Attack** — Forces users off real AP to connect to the fake one.
* 🔐 **Credential Capture** — Prompts for Wi-Fi password on connection.
* 💡 **Status LED** — Shows connection activity using built-in LED.

---

## 📷 Screenshots

<details>
  <summary><b>Admin Panel UI</b></summary>
  <img src="https://drive.google.com/file/d/1DISuFLV0Ek-K5RDqGzAa3qY90Z9hpXii/view?usp=drive_link" alt="Admin UI preview"/>
</details>

<details>
  <summary><b>Password Prompt Page</b></summary>
  <img src="https://drive.google.com/file/d/1xFgIXYwax4HY6TbnaaAu38Al0UwOVAt1/view?usp=drive_link" alt="Password prompt"/>
</details>

---

## 📦 Requirements

* ESP8266 Board (e.g., NodeMCU, Wemos D1 Mini)
* Arduino IDE or PlatformIO
* Libraries:

  * `ESP8266WiFi`
  * `ESP8266WebServer`
  * `DNSServer`

---

## 🛠️ Installation

1. **Install the ESP8266 Board Package**
   In Arduino IDE → Board Manager → Search for `ESP8266` → Install.

2. **Clone the Repository**

   ```bash
   git clone https://github.com/yourusername/esp8266-evil-twin.git
   cd esp8266-evil-twin
   ```

3. **Upload the Code**

   * Open the project in Arduino IDE
   * Select your ESP8266 board and correct COM port
   * Upload

---

## 🌐 Captive Portal Behavior

| OS        | Triggered URL Path                      |
| --------- | --------------------------------------- |
| Android   | `/generate_204`, `/gen_204`             |
| Windows   | `/fwlink`, `/ncsi.txt`                  |
| iOS/macOS | `/hotspot-detect.html`, `/success.html` |
| Linux     | `/nm`, `/nm.index.html`                 |
| ChromeOS  | `/checkconnectivity.txt`                |

---

## 🧠 How It Works

1. **Scan nearby Wi-Fi networks** and list them via the admin interface.
2. **Select a target SSID + BSSID.**
3. Activate:

   * `Start EvilTwin` → Creates a fake AP with identical SSID.
   * `Start deauthing` → Sends deauth frames to kick users off the real AP.
4. Users connect to the fake AP and are shown a **fake login form**.
5. Submitted password is attempted for connection:

   * If valid: teardown fake AP and log success.
   * If invalid: show error and keep portal open.

---

## 🚨 Legal Disclaimer

This software is provided **for educational purposes only.**
The author is not responsible for any misuse or damage caused by this tool.

> Always have **explicit permission** before testing or demonstrating these techniques on any network.

---

## 📝 License

This project is licensed under the [MIT License](LICENSE).

---

## 💬 Contributions & Feedback

Feel free to open Issues or Pull Requests. Contributions are welcome!

---

Let me know if you'd like me to include custom screenshots, update the HTML preview, or create a Wiki/tutorial section for users.
