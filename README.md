# ⌨️ Educational Keystroke & Window Focus Logger

> A modular Python educational keylogger designed to demonstrate input capture mechanics, active window context correlation, log rotation, and secure remote webhook alerting for defensive research.

[![Author](https://img.shields.io/badge/Made%20by-cyber--atharv-00ffcc?style=flat-square&logo=github)](https://github.com/cyber-atharv)
[![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=flat-square&logo=python&logoColor=white)](https://www.python.org)
[![License](https://img.shields.io/badge/License-MIT-blue.svg?style=flat-square)](LICENSE)

---

## 📌 What is a Keylogger?

A **keylogger** is a software or hardware utility that records the keys struck on a keyboard. In cybersecurity, understanding how input capture mechanisms work is vital for:
- Writing Endpoint Detection and Response (EDR) rules that detect unauthorized API hooking (like `SetWindowsHookEx` or event tap listeners).
- Understanding how attackers correlate captured keystrokes with active browser windows (e.g. capturing credentials entered on specific login pages).

This educational tool, crafted by **cyber-atharv**, demonstrates clean multi-threaded input event capture, window title tracking, local log rotation, and optional webhook telemetry.

---

## ✨ Key Features

- **Microsecond Timestamping:** Every key event records the exact time and whether it was a regular alphanumeric character or a special control key (Enter, Backspace, Ctrl, Shift).
- **Active Window Tracker:** Automatically checks and attaches the current foreground window title (works across Windows, macOS, and Linux).
- **Runtime Toggle Switch (`F9`):** Press `F9` at any time to immediately pause or resume keystroke recording.
- **Log Management & Rotation:** Writes events to structured log files and automatically rolls over when files exceed a threshold (e.g. 5MB) to avoid filling disk space.
- **Optional Webhook Forwarding:** Simulates telemetry exfiltration by dispatching batched logs to an authorized endpoint over HTTPS.

---

## 🚀 Quick Start & Usage

### 1. Installation
```bash
cd keylogger
pip install -r requirements.txt # or pip install pynput requests pywin32
```

### 2. Running the Keylogger
```bash
python keylogger.py
```

- Keystrokes will begin logging to `logs/keylog.txt`.
- Press **F9** to pause or resume recording.
- Press **Ctrl + C** in the terminal to stop cleanly.

---

## 🧠 Why I Built This

I built this project to understand how operating system event loops intercept input before applications receive them, and how forensic investigators analyze keystroke logs to uncover unauthorized access. Building it defensively taught me the importance of endpoint privilege management and anti-hooking mechanisms.

---

## ⚠️ Strict Legal & Ethical Disclaimer

> **Educational & Research Use Only:** Keylogging without explicit, documented consent is strictly illegal under cyber laws worldwide. This script is provided exclusively for lab study, cybersecurity education, and defensive monitoring research.

---

## 📜 Author & License

- **Author:** [cyber-atharv](https://github.com/cyber-atharv)
- **License:** Open source under the MIT / AGPL License.
