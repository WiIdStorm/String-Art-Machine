# String-Art-Machine
An automated String Art machine that performs both the automated nailing process and the string weaving process.

## Introduction

This project presents an automated String Art machine designed to handle both the automated nailing and string weaving processes. The system architecture integration and control flow are built upon the following core components:

* **Control Unit & Embedded System:** Powered by an **ESP32-WROOM-32** microcontroller managing real-time motion control, sensor data processing, and execution commands.
* **Software & Image Processing:** A **Python**-based framework is utilized to convert digital source images into optimized string-path coordinates and numerical control data.
* **Position Tracking & Feedback System:** To ensure high-precision positioning and prevent accumulative mechanical errors during operation, the system employs a robust feedback mechanism:
  * A **NEMA23 Closed-Loop Stepper Motor** with an integrated encoder to prevent step loss.
  * **Optical Limit Switch Endstops** serving as red-light sensors for precise homing, position validation, and path tracking.

## Hardware Components

The primary hardware and mechatronic components utilized in this project are listed below:

### 1. Controllers & Microcontrollers
* **Microcontroller:** ESP32-WROOM-32 (Handles real-time motion control and sensor data processing).

### 2. Actuators, Drivers & Encoders
* **Motor & Driver Assembly:** NEMA23 Closed Loop Stepper Motor (2.3 Nm, Model: CS-M22323) paired with a **CS-D508** encoder-integrated stepper motor driver.

### 3. Power Supplies (SMPS)
The system utilizes dedicated Switch Mode Power Supplies to separate power stages for stability:
* **48V Supply:** MT-500-48 (48V, 10A SMPS) - Powering the main motor drivers.
* **36V Supply:** MT-350-36 (36V, 10A SMPS).
* **24V Supply:** Mervesan MT-250-24 (24VDC, 10A SMPS).

### 4. Voltage Regulation (DC-DC Step-Down)
* **High-Power Buck Converters:** 2x **XL4016** (300W, 10A DC-DC Step Down Regulator Modules). 
  * *Note on Implementation:* One of these buck converters replaces a standard 4-38V 5A step-down module, as the high-capacity XL4016 was readily available and deployed to maintain power consistency across the logic and sensor circuits.

### 5. Sensors & Position Tracking
* **Optical Sensors:** Optical Limit Switch Endstops (Dimensions: 33 x 12 x 10 mm) used for precise homing, position validation, and path tracking.
