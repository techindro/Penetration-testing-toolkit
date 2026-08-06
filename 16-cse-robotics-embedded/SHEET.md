# 🤖 Module 16: Robotics & Embedded Systems Troubleshooting Guide

Troubleshooting guide for ROS/ROS2 node errors, serial port permissions (`/dev/ttyUSB0`), ESP32 / Arduino IDE flashing issues, and hardware interfacing bugs.

---

## 🔌 1. Serial Port Permission Denied (`/dev/ttyUSB0` or `/dev/ttyACM0`)

### Symptom:
`can't open device "/dev/ttyUSB0": Permission denied` when uploading code from Arduino IDE or flashing ESP32.

### Fix:
```bash
# Add current user to dialout group
sudo usermod -a -G dialout $USER

# Grant temporary permissions
sudo chmod 666 /dev/ttyUSB0

# Log out and log back in for group changes to take effect!
```

---

## 🤖 2. ROS2 (Robot Operating System) Environment Setup

### Environment Sourcing Fix:
```bash
# Source ROS2 Humble / Iron setup script in ~/.bashrc
echo "source /opt/ros/humble/setup.bash" >> ~/.bashrc
source ~/.bashrc

# Verify ROS2 Installation:
ros2 doctor
```

---

## ⚡ 3. ESP32 / ESP8266 Board Flashing Error

### Symptom:
`A fatal error occurred: Failed to connect to ESP32: Timed out waiting for packet header`

### Fix:
1. Hold down the physical **BOOT** button on the ESP32 board while uploading until `Writing at 0x00010000...` appears in Arduino IDE console.
2. Install CP210x or CH340 USB-to-UART bridge drivers on Windows/Linux.
