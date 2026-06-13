# final-year-project

https://drive.google.com/drive/u/0/folders/1e7n-i6c-wgyNvAkc0vsrrqZMyImXZucF
# IoT-Enabled Motion Control and Position Monitoring System Using MPU9250 and Machine Learning

An intelligent **IoT-enabled robotic arm system** that performs **real-time motion control and position monitoring** using the **MPU9250 sensor**, **Machine Learning (CatBoost)**, and wireless communication. The system captures hand motion, predicts servo motor angles, and controls a robotic arm smoothly in real time.

---

## Project Overview

Traditional robotic motion-control systems are often expensive, complex, and require multiple sensors. This project provides a **low-cost and efficient solution** using a **single MPU9250 IMU sensor** for motion tracking and **Machine Learning (CatBoost Regression)** for real-time prediction of servo motor positions.

The system captures hand gestures and motion data through the MPU9250 sensor attached to the user's hand. A **Raspberry Pi Zero 2W** processes the sensor values and predicts servo motor angles using a trained **CatBoost Machine Learning model**. The predicted values are transmitted wirelessly to the **ESP32**, which controls the robotic arm using **PCA9685 PWM Driver** and servo motors.

---

## Features

- Real-time hand gesture-based robotic arm control
- MPU9250-based motion and position tracking
- Machine Learning using **CatBoost Regression**
- Wireless communication using Bluetooth/Wi-Fi
- Smooth robotic arm movement with jitter reduction
- Multi-axis robotic arm control
- IoT-enabled motion transmission
- Low-cost and scalable system

---

## Hardware Components

- **Raspberry Pi Zero 2W** – Main controller for sensor processing and ML execution
- **MPU9250 Sensor** – Motion tracking using accelerometer and gyroscope
- **ESP32** – Wireless receiver and communication controller
- **PCA9685 PWM Driver** – Servo motor controller
- **Servo Motors** – Multi-axis robotic arm movement
- **Acrylic Robotic Arm Structure**
- **External Power Supply/Battery**

---

## Software Requirements

### Raspberry Pi Side
- Raspberry Pi OS Legacy (64-bit)
- Python 3.x
- MobaXterm (SSH access)

### ESP32 Side
- Arduino IDE
- ESP32 Board Package

---

## Libraries Used

### Transmission Side (Raspberry Pi)

```python
smbus
numpy
pandas
catboost
serial
time
math
mpu9250_jmdev
```

### Receiver Side (ESP32)

```cpp
Wire.h
BluetoothSerial.h
Adafruit_PWMServoDriver.h
```

---

## Machine Learning Model

### CatBoost Regression Model

This project uses a **CatBoost Regression Model** to improve robotic arm movement accuracy.

### Why CatBoost?

CatBoost is used because it:

- Provides high prediction accuracy
- Works efficiently on sensor datasets
- Reduces noise impact
- Improves real-time prediction performance
- Handles complex motion patterns effectively

### Model Workflow

1. MPU9250 captures:
   - Accelerometer values (X, Y, Z)
   - Gyroscope values (X, Y, Z)

2. Sensor data preprocessing:
   - Noise filtering
   - Missing value handling
   - Normalization

3. CatBoost model training:
   - Input → Sensor values
   - Output → Servo motor angles

4. Real-time prediction:
   - Model predicts servo positions
   - Predicted values sent to ESP32

5. Servo control:
   - ESP32 controls robotic arm movement smoothly

---

## System Architecture

```text
Hand Movement
      ↓
MPU9250 Sensor
      ↓
Raspberry Pi Zero 2W
(Data Processing + ML Prediction)
      ↓
Bluetooth / Wi-Fi
      ↓
ESP32 Controller
      ↓
PCA9685 PWM Driver
      ↓
Servo Motors
      ↓
Robotic Arm Movement
```

---

## Working Methodology

### Hardware Methodology

- MPU9250 captures real-time hand motion.
- Raspberry Pi receives sensor data through I2C communication.
- Motion data is processed in real time.
- Predicted servo commands are sent wirelessly to ESP32.
- PCA9685 generates PWM signals.
- Servo motors move the robotic arm accordingly.

### Software Methodology

- Sensor data collection
- Data preprocessing
- Motion mapping
- CatBoost model prediction
- Wireless transmission
- Smooth servo movement with jitter reduction

---

## Applications

- Gesture-based robotic arm control
- Industrial automation
- Object handling systems
- Medical rehabilitation support
- Assistive systems for physically challenged people
- Remote robotic control
- Human motion tracking
- Pick-and-place robotic operations
- Robotics and AI research

---

## Project Output

The robotic arm mimics hand movements in real time using the MPU9250 sensor and Machine Learning predictions. Motion data is processed by Raspberry Pi and transmitted wirelessly to ESP32 for smooth robotic arm control.

---

## Folder Structure

```text
project/
│── dataset/
│── model/
│   └── catboost_model.pkl
│── raspberry_pi/
│   └── realtime_mpu_control.py
│── esp32/
│   └── robotic_arm_control.ino
│── images/
│── README.md
```

---

## Installation Steps

### Clone Repository

```bash
git clone <your-github-link>
cd project-name
```

### Install Python Dependencies

```bash
pip install numpy pandas catboost pyserial smbus2
```

### Run Raspberry Pi Code

```bash
python realtime_mpu_control.py
```

### Upload ESP32 Code

1. Open Arduino IDE
2. Select ESP32 Board
3. Upload `robotic_arm_control.ino`

---

## Future Scope

- AI-based gesture recognition
- Cloud monitoring system
- Mobile app integration
- Advanced robotic precision
- Voice-controlled robotic arm
- Healthcare rehabilitation improvements

---

## Team Members

- Apeksha Bhagwan Ugale
- Mayuri Mangesh Yende
- Shravani Narendra Mahalle
- Sakshi Padmakar Yeole

### Guide
**Prof. Vishalsinh V. Bais**

### Department
Computer Science and Engineering  
Prof. Ram Meghe College of Engineering and Management, Badnera

## References

Research papers and IEEE publications used in this project are available in the project documentation and PPT.


## Project Status

✅ Completed  
🚀 Real-time robotic arm movement implemented



## License

This project is developed for **academic and educational purposes**.
