# ESP32-LED-Control
ESP32-based system that controls an onboard LED via HTTP GET requests. Demonstrates basic IoT communication and remote hardware control.

A compact IoT system using the ESP32 microcontroller to remotely toggle an onboard LED based on server responses. It showcases real-time communication between hardware and web services using HTTP.

---

## 📘 Project Overview
This setup allows the ESP32 to connect to Wi-Fi and send periodic HTTP GET requests to a remote server. The server responds with either `0` or `1`, which determines the LED state (OFF or ON). Designed for simple remote control and monitoring via web endpoints.

- **Retrieve LED status:** [`retrieve.php`](https://s-m.com.sa/r2/test/retrieve.php)  
- **Send LED command:** [`send.php`](https://s-m.com.sa/r2/test/send.php?x=1)

---

## 🔧 Key Features
- Dynamic Wi-Fi connection using `WiFiMulti`
- HTTP GET-based control logic
- LED toggling based on server response
- Serial output for debugging and status tracking
- Clean, modular code for future scalability

---

## 🛠️ Technologies Used
- ESP32 board
- Arduino IDE
- Libraries: `WiFi.h`, `HTTPClient.h`
- Serial Monitor for live feedback
- Web-based endpoints for data exchange

---

## 🔄 Workflow
1. ESP32 connects to Wi-Fi using stored credentials
2. Sends GET request to `retrieve.php`
3. Parses response and converts to integer
4. Turns LED ON if response is `1`, OFF if `0`
5. Prints status to Serial Monitor every 5 seconds

---

## ⚠️ Challenges & Solutions

| Challenge                        | Solution                                                   |
|----------------------------------|-------------------------------------------------------------|
| Unstable Wi-Fi connection        | Used `WiFiMulti` to manage multiple networks               |
| Parsing HTTP response            | Used `toInt()` and validated input                         |
| Handling server errors/timeouts  | Applied `http.errorToString()` and conditional checks      |
| Syncing LED with server state    | Added polling delay for consistent updates                 |

---

## 🚀 Future Improvements
- Add POST support to send sensor data
- Include physical button for manual override
- Display status on OLED screen
- Secure communication via HTTPS and tokens
- Expand control to multiple outputs (e.g., motors, relays)

---

📌 *Built for educational and prototyping purposes using ESP32 and basic web integration.*
