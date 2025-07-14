# gestureOledWifiSetupHTTPpush-v2

An advanced ESP32-C6 project that combines gesture recognition, OLED UI, web-based configuration, and HTTP push integration.

---

## 📦 Features

- 👋 **Gesture Input** using PAJ7620U2 sensor (via RevEng_PAJ7620 library)
- 🖥️ **OLED Display** with status, gesture, action, and IP info (U8g2lib)
- 🌐 **Wi-Fi Setup** via Captive Portal (AP mode if not configured)
- 🛜 **HTTP Push Actions**: Configurable POST actions for up to 9 gestures
- ⚙️ **Web Configuration UI** for gesture-action mapping
- 🔁 **System Recovery Logic** for gesture sensor, SPIFFS, and Wi-Fi
- 💡 **Dark Mode** and responsive UI in web server
- 🗂 **SPIFFS Storage** for gesture config, logs, and flash stats
- 📈 **SSE (Server-Sent Events)** for real-time logs and display updates
- 🔘 **Physical Reset Button** to erase Wi-Fi settings (GPIO2)
- 🕹️ **Live Logs** and action feedback via OLED and Web UI

---

## 🧠 Gesture Mapping

Supported gestures:
- Right
- Left
- Up
- Down
- Forward
- Backward
- Clockwise
- Anticlockwise
- Wave

Each gesture can trigger one or more HTTP POST actions with JSON payloads.

---

## 📺 Display Info (OLED)

The display cycles through:
- Connection status
- Last gesture detected
- Last action triggered
- Device IP address

If text exceeds screen width, it scrolls smoothly.

---

## 🌐 Web Interface Endpoints

| Endpoint      | Description                        |
|---------------|------------------------------------|
| `/`           | Main UI with logs & gesture status |
| `/config`     | Gesture-to-Action configuration    |
| `/wifiSetup`  | Captive portal for Wi-Fi config    |
| `/logs`       | JSON output of recent logs         |
| `/exportGestures` | Export configuration (JSON)   |
| `/importGestures` | Import configuration (JSON)   |

---

## 🔧 Hardware Requirements

- [XIAO ESP32-C6](https://www.seeedstudio.com/XIAO-ESP32C6-p-5717.html)
- PAJ7620U2 Gesture Sensor
- SSD1306 128x64 OLED (I²C)
- (Optional) TFT Display for log output
- Momentary Push Button on GPIO2

---

## 📚 Libraries Used

| Library                    | Version        |
|----------------------------|----------------|
| U8g2lib                    | 2.35.30        |
| RevEng_PAJ7620             | 1.5.0          |
| ESPAsyncWebServer          | 3.7.6          |
| ArduinoJson                | 7.2.1          |
| HTTPClient (built-in)      | Arduino Core   |
| Preferences (built-in)     | Arduino Core   |

---

## 🛠️ Flash Size Management

- Web-configurable gesture actions are stored in SPIFFS as `.json` files.
- Flash statistics are shown live in the UI and sent via SSE.

---

## 💡 Tips

- Press and hold the reset button (GPIO2) for 3 seconds to clear saved Wi-Fi settings and enter AP mode.
- Gesture action mappings can be saved, exported, and imported via `/config`.
- OLED scrolls long strings automatically to stay readable.

---

## 🧑‍💻 Developed by

**Jesse Greene**  
Berlin, Germany  
> Designed for performance, resilience, and style.
