# CHRONOS-4 : Tactical Quadrupedal Robotics Platform

CHRONOS-4 (formerly SPECTER-ZERO) is an advanced, bio-inspired four-legged robotic platform engineered using an ESP32 microcontroller architecture. The system features a custom asynchronous local web server for real-time kinematic wireless controls, a dynamically managed interruptible smart timing engine for fluent gait tracking, and a dedicated secondary I2C telemetry pipeline displaying real-time diagnostics on an OLED interface.

---

## 🚀 Key Features

- **Asynchronous Wireless Control:** Hosts a local WiFi Access Point (`CHRONOS-QUAD-ROBOT`) utilizing an asynchronous server configuration to handle overlapping kinematic HTTP requests instantly without blocking processing cycles.
- **Dynamic Gait Kinematics:** Custom-calibrated, multi-phase loops executing fluid `Forward Creep`, `Backward Recess`, `Omnidirectional Turning`, and adaptive `Sit/Stand` routines.
- **Smart Timing Engine:** Operates via non-blocking, interruptible state-checking mechanics (`pressingCheck`) ensuring instant command override capability during execution.
- **Real-Time Telemetry Dashboard:** Isolated secondary data pipeline pushing live hardware states, system commands, and custom low-power status expressions to an SSD1306 OLED interface.
- **Cohesive Chassis Stability:** Automated center-of-mass balancing routines ensuring consistent body propulsion glide and structural load distribution across all 4 limbs.

---

## 🛠️ System Architecture & Hardware Stack

The hardware layer is engineered for high stability, distinct power management separation, and modular communication protocols:

- **Main Processing Unit:** ESP32 NodeMCU Development Board
- **Actuation Driver:** PCA9685 16-Channel 12-bit PWM I2C Servo Driver
- **Actuators:** High-Torque Metal-Gear Servos (MG996R / SG90 configurations)
- **Visual Diagnostics Layer:** SSD1306 128x64 I2C OLED Display
- **Power Management:** Isolated Dual-Rail Power Distribution (Separated Logic Supply vs. High-Current Servo Rail to prevent ESP32 voltage brownouts).

---

## 📂 Repository Structure

```text
├── firmware.ino      # Main Unified Controller (Web Server, Kinematics, OLED & Core Loop)
└── README.md             # Project Documentation
