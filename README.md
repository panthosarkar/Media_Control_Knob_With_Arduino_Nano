# 🎚️ Arduino Nano Volume Knob for Windows

A DIY physical **volume controller** using an **Arduino Nano** and **rotary encoder**, with extended functionality like **play/pause**, **mute**, and **track switching**, interpreted via a **Python script** on Windows.

## 🧩 Overview

This project creates a smart media knob that communicates via USB to control system volume and media playback on Windows. It detects rotary and button actions and sends serial commands to a Python script, which then interacts with the operating system.

## ⚙️ Features

- 🔊 Rotate to increase/decrease system volume
- ⏯️ Single-click: Toggle Play/Pause
- 🔇 Double-click: Mute system audio
- 🔁 Long press: Switch between Volume Mode and Media Mode
- ⏭️ Rotate in Media Mode: Play Next/Previous Track
- 🧠 Includes debounce, double-click, and long-hold detection logic

## 🔧 Hardware Requirements

- Arduino Nano (or compatible board)
- Rotary Encoder (with push button)
- USB Cable (for Arduino connection)
- Windows PC with Python 3 installed

## Circuit Diagram

["./images/Circuit.png]

## 🛠 Software Setup

### Arduino Code

1. Open `arduino/volume_knob.ino` in the Arduino IDE
2. Select the correct board (Arduino Nano) and port
3. Upload the sketch to your Arduino

### Python Script

1. Install required Python libraries:

```bash
pip install pyserial pycaw comtypes
```

2. Edit the COM port in `python/volume_control.py` to match your Arduino port
3. Run the script:

```bash
   python python/volume_control.py
```

## 🧪 How It Works

### Modes:

- **Mode 1 (default):** Rotary controls volume
- **Mode 2:** Rotary controls media tracks (next/prev)

### Serial Commands Sent by Arduino:

| Command   | Meaning               |
| --------- | --------------------- |
| 0 to 100  | Set system volume     |
| play      | Toggle play           |
| pause     | Toggle pause          |
| mute      | Mute audio            |
| nexttrack | Next media track      |
| prevtrack | Previous media track  |
| mode1     | Switch to Volume Mode |
| mode2     | Switch to Media Mode  |

These commands are parsed and executed by the Python script using Windows APIs.

## 📦 Python Requirements

- pyserial
- pycaw
- comtypes

Install using pip:

```bash
pip install pyserial pycaw comtypes
```

## 📓 Notes

- Make sure your Arduino is recognized under Device Manager (COM port)
- The Python script must remain running in the background to process input
- If system volume doesn't respond, try running the Python script as administrator
- Compatible with most modern media apps (Spotify, VLC, etc)
- If you don't want to run python script every time you boot, then follow these steps
  - press _win + R_ then type _shell:startup_
  - copy the _pyw_ file and paste it to that folder
  - restart your pc and you are good to go.

## 🪪 License

MIT License

You are free to use, modify, and distribute this project as you wish. Attribution is appreciated.

## 👨‍💻 Author

Made with ❤️ by Pantho Sarkar

Pull requests and contributions are welcome!

```

```
