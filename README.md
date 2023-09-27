# Rocket Control System

This repository contains the source code for a rocket control system that uses an Arduino board with various sensors and actuators. The system is designed to control a model rocket's flight parameters, log sensor data, and communicate with a ground station over LoRa.

## Table of Contents

- [Features](#features)
- [Hardware Requirements](#hardware-requirements)
- [Software Requirements](#software-requirements)
- [Installation](#installation)
- [Usage](#usage)
- [Calibration](#calibration)
- [Contributing](#contributing)
- [License](#license)

## Features

- **IMU Integration**: Utilizes an MPU6050 sensor for accurate Inertial Measurement Unit (IMU) data.
- **GPS**: Integrates with a GPS module for location and satellite data.
- **PID Control**: Implements PID control for pitch, roll, and yaw stabilization.
- **LoRa Communication**: Sends sensor data and rocket status to a ground station via LoRa.
- **Parachute Deployment**: Deploys a parachute at a specified altitude based on sensor data.
- **Data Logging**: Logs sensor data to an SD card for post-flight analysis.

## Hardware Requirements

To run this code, you'll need the following hardware components:

- Arduino board (e.g., mega or stm32)
- MPU6050 accelerometer and gyroscope module
- BMP180 or BMP085 barometric pressure sensor
- GPS module (e.g., NEO-6M)
- Servo motors for pitch, yaw, and roll control
- Parachute deployment servo motor
- SD card module for data logging
- LoRa module (e.g., SX1278 or compatible)
- Buzzer and LED for status indication


## Software Requirements

You'll need the following software:

- Arduino IDE (https://www.arduino.cc/en/software)
- Required Arduino libraries (Adafruit MPU6050, Adafruit BMP085, Adafruit GPS, PID_v1, TinyGPS++, SoftwareSerial, and LoRa)
- will add a processing flight telemetrty visulizer soon
## Installation

1. Clone this repository to your local machine:

   ```shell
   git clone https://github.com/your-username/rocket-control-system.git
   Open the Arduino IDE and load the rocket_control_system.ino sketch.

Install the required libraries using the Arduino Library Manager:

- Adafruit MPU6050
- Adafruit BMP085 (or BMP180)
- Adafruit GPS
- PID_v1
- TinyGPS++
- SoftwareSerial
- LoRa
- Configure the Arduino IDE for your specific board(download stm32 manager for stm32 board)

# Usage
Before launching the rocket, ensure that you have calibrated the MPU6050 sensor by following the calibration procedure described below.

# Calibration:

To calibrate the MPU6050 sensor, you can send a calibration command to the Arduino board either via serial communication or LoRa. Make sure the rocket is on a flat, stable surface and not moving during calibration.

shell
Copy code
Send calibration command over serial (replace COMx with your serial port)
echo "CALIBRATE" > COMx
Launch:

After calibration, you can initiate the rocket launch. Once the rocket reaches the target altitude and conditions are met, the system will automatically deploy the parachute. The status and sensor data will be transmitted via LoRa to a ground station.

# Monitoring:

You can monitor the rocket's status and data from the ground station. The transmitted data includes pitch, roll, yaw angles, altitude, latitude, and longitude.

# Calibration
Calibrating the MPU6050 sensor is a crucial step to ensure accurate measurements. During calibration, the sensor should be placed on a flat and stable surface, and the calibration command should be sent.

Ensure the rocket is on a stable surface.
Send the calibration command to the Arduino (as shown in the Usage section).
Wait for the calibration process to complete. The offsets will be printed to the Serial Monitor.
# Contributing
Contributions are welcome! If you'd like to contribute to this project, please follow these steps:
for now i would love my teamates to contribute 

Fork the repository.
Create a new branch for your feature or bug fix.
Make your changes.
Test your changes thoroughly.
Create a pull request with a clear description of your changes.
# License
This project is licensed under the MIT License. See the LICENSE file for details.





