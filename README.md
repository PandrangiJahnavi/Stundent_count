# Smart Student Attendance Counter using ESP32, HC-SR04, OLED, and ThingSpeak

## Overview

This project is an IoT-based Smart Student Attendance Counter that automatically counts the number of students entering and exiting a classroom using two HC-SR04 ultrasonic sensors.

The system displays the current student count on an OLED display and uploads the attendance data to ThingSpeak for real-time cloud monitoring and analytics.

## Features

* Automatic student counting
* Entry and exit detection
* Real-time attendance tracking
* OLED display visualization
* Cloud monitoring using ThingSpeak
* Wi-Fi-enabled ESP32 system
* Debounce protection to prevent false counts
* Real-time serial monitoring

## Components Required

* ESP32 Development Board
* 2 × HC-SR04 Ultrasonic Sensors
* SSD1306 OLED Display (128×64)
* Breadboard
* Jumper Wires
* Wi-Fi Connection

## Pin Connections

### Ultrasonic Sensor A (Inside)

| HC-SR04 | ESP32   |
| ------- | ------- |
| TRIG    | GPIO 5  |
| ECHO    | GPIO 18 |

### Ultrasonic Sensor B (Outside)

| HC-SR04 | ESP32   |
| ------- | ------- |
| TRIG    | GPIO 13 |
| ECHO    | GPIO 12 |

### OLED Display

| OLED | ESP32   |
| ---- | ------- |
| VCC  | 3.3V    |
| GND  | GND     |
| SDA  | GPIO 21 |
| SCL  | GPIO 22 |

## Working Principle

### Student Entering

1. Sensor A detects a person first.
2. Sensor B detects the same person shortly after.
3. Student count increases by 1.
4. OLED display updates automatically.
5. Data is uploaded to ThingSpeak.

### Student Exiting

1. Sensor B detects a person first.
2. Sensor A detects the same person shortly after.
3. Student count decreases by 1.
4. OLED display updates automatically.
5. Updated data is uploaded to ThingSpeak.

## Detection Logic

### Entry Detection

```text
Sensor A → Sensor B
Count = Count + 1
```

### Exit Detection

```text
Sensor B → Sensor A
Count = Count - 1
```

## OLED Display Output

```text
Students:
15
```

## Serial Monitor Output

### Student Entering

```text
ENTER → count: 16
STUDENT PRESENT: 16
Channel update successful.
```

### Student Exiting

```text
EXIT → count: 15
STUDENT PRESENT: 15
Channel update successful.
```

## ThingSpeak Data

| Field   | Data          |
| ------- | ------------- |
| Field 1 | Student Count |

The student attendance data is stored in the cloud and can be viewed through ThingSpeak charts and dashboards.

## Applications

* Smart Classroom Management
* College Attendance Monitoring
* Library Occupancy Tracking
* Laboratory Access Monitoring
* Office Employee Counting
* Building Occupancy Management

## Technologies Used

* ESP32
* HC-SR04 Ultrasonic Sensors
* SSD1306 OLED Display
* ThingSpeak Cloud Platform
* Wi-Fi Communication
* Arduino IDE
* Embedded C/C++

## Future Enhancements

* RFID Student Identification
* Face Recognition Attendance System
* Mobile App Dashboard
* AWS Cloud Integration
* Real-Time Attendance Analytics
* Email and SMS Notifications
* Multi-Classroom Monitoring

## Project Architecture

```text
HC-SR04 Sensors
       ↓
     ESP32
       ↓
 OLED Display
       ↓
   Wi-Fi
       ↓
 ThingSpeak Cloud
```

## Project Level

### Level 1

Student counting using ultrasonic sensors.

### Level 2

Real-time OLED display monitoring.

### Level 3

Cloud-based attendance monitoring using ThingSpeak.

#OUTPUT
https://github.com/PandrangiJahnavi/Stundent_count/blob/main/Screenshot%202026-06-15%20095714.png
https://github.com/PandrangiJahnavi/Stundent_count/blob/main/Screenshot%202026-06-15%20095748.png

## Author

**Pandrangi Jahnavi**

B.E. Electronics and Communication Engineering (ECE)

IoT | Embedded Systems | Cloud Computing | Smart Classroom Solutions
