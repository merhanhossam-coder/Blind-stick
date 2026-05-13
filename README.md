# Ultrasonic Distance Alarm System

[cite_start]This project features an Arduino-based system that utilizes an **HC-SR04 Ultrasonic Sensor** to detect the proximity of objects[cite: 1, 2]. [cite_start]When an object moves within a predefined threshold, the system triggers both a visual and an audible alert.

---

### 🛠 Features
* [cite_start]**Distance Measurement**: Calculates distance in both centimeters and inches.
* [cite_start]**Threshold Alert**: Automatically triggers peripherals when an object is closer than 40cm.
* [cite_start]**Visual & Audio Feedback**: Uses an LED and a Buzzer as indicators[cite: 1, 2].
* [cite_start]**Live Debugging**: Outputs distance readings directly to the Serial Monitor at 9600 baud[cite: 1, 2].

### 🔌 Pin Mapping
| Component | Arduino Pin | Mode |
| :--- | :--- | :--- |
| **Trig Pin** | Pin 6 | [cite_start]`OUTPUT` [cite: 1, 2] |
| **Echo Pin** | Pin 7 | [cite_start]`INPUT` [cite: 1, 2] |
| **LED** | Pin 4 | [cite_start]`OUTPUT` [cite: 1, 2] |
| **Buzzer** | Pin 5 | [cite_start]`OUTPUT` [cite: 1, 2] |

### 🚀 How It Works
1.  [cite_start]**Triggering**: The Arduino sends a short 2-microsecond `LOW` pulse followed by a 10-microsecond `HIGH` pulse to the ultrasonic sensor's trigger pin[cite: 1, 3].
2.  [cite_start]**Calculation**: The sensor measures the time it takes for the sound wave to bounce back (`duration`)[cite: 1, 3].
3.  **Conversion**: The distance is calculated using the following formulas:
    * [cite_start]$distanceCm = \frac{duration \times 0.034}{2}$ [cite: 1, 3]
    * [cite_start]$distanceInch = \frac{duration \times 0.0133}{2}$ [cite: 1, 3]
4.  **Logic**: 
    * [cite_start]If `distanceCm` is less than 40, the Buzzer and LED turn **ON**[cite: 1, 5].
    * [cite_start]If the distance is greater than 40, both indicators turn **OFF**[cite: 1, 6].

### 📂 Setup and Installation
1.  [cite_start]**Connect Hardware**: Wire the components according to the pin mapping table above.
2.  [cite_start]**Upload Code**: Open the `.ino` file in the Arduino IDE and upload it to your board[cite: 1, 2].
3.  [cite_start]**Monitor**: Open the **Serial Monitor** (9600 baud) to view real-time distance updates[cite: 1, 2, 4].

---
> [cite_start]**Note**: The alert threshold can be customized by changing the value in the `if(distanceCm < 40)` statement within the code.

