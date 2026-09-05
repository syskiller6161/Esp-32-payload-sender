# ESP32 File Sender

Send files from ESP32 to any device (PS4, Phone, PC, etc.) over WiFi using SoftAP.

---

## Features

- Create WiFi Access Point 
- Upload any file through web interface
- Send file to any device connected to the ESP32 via TCP
- Change WiFi name and password from the web page
- Show connected devices
- Progress bar while uploading and sending

---

## Default WiFi

- **SSID:** `ESP32-FileSender`
- **Password:** `12345678`
- **Web Interface:** [http://192.168.4.1](http://192.168.4.1)

---

## How to Use

1. Flash the `payload_sender.bin` file to your ESP32
2. Connect your phone/PC to the WiFi `ESP32-FileSender`
3. Open browser and go to → **http://192.168.4.1**
4. Upload your file
5. Enter the target IP and Port (or select from connected devices)
6. Click **Send File**

---

## Flashing the Firmware

### Method 1: ESP Web Flasher (Easiest)

1. Go to: [https://espressif.github.io/esptool-js/](https://espressif.github.io/esptool-js/)
2. Connect your ESP32
3. Click **Connect**
4. Add the file `payload_sender.bin`
5. Set address to `0x10000`
6. Click **Program**

### Method 2: esptool (Command Line)

```bash
python -m esptool --chip esp32 --port COM3 --baud 460800 write_flash -z 0x10000 payload_sender.bin
