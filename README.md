# Ultrasonic Distance Alarm System

This project features an Arduino-based system that utilizes an **HC-SR04 Ultrasonic Sensor** to detect the proximity of objects

---

### 🛠 Features
**Distance Measurement**: Calculates distance in both centimeters and inches.
**Threshold Alert**: Automatically triggers peripherals when an object is closer than 40cm.
**Visual & Audio Feedback**: Uses a Buzzer as indicators.
**Live Debugging**: Outputs distance readings directly to the Serial Monitor at 9600 baud.

### 🔌 Pin Mapping
| Component | Arduino Pin | Mode |
| :--- | :--- | :--- |
| **Trig Pin** | Pin 6 | `OUTPUT`  |
| **Echo Pin** | Pin 7 | `INPUT`  |
| **Buzzer** | Pin 5 | `OUTPUT`  |

### 🚀 How It Works
1.  **Triggering**: The Arduino sends a short 2-microsecond `LOW` pulse followed by a 10-microsecond `HIGH` pulse to the ultrasonic sensor's trigger pin.
2.  **Conversion**: The distance is calculated using the following formulas:
    * $distanceCm = \frac{duration \times 0.034}{2}$ 
    * $distanceInch = \frac{duration \times 0.0133}{2}$ 
3.  **Logic**: 
    * If `distanceCm` is less than 40, the Buzzer make a sound
    * If the distance is greater than 40, both indicators turn **OFF**.

### 📂 Setup and Installation
1.  **Connect Hardware**: Wire the components according to the pin mapping table above.
2.  **Upload Code**: Open the `.ino` file in the Arduino IDE and upload it to your board.
3.  **Monitor**: Open the **Serial Monitor** (9600 baud) to view real-time distance updates.

---
> **Note**: The alert threshold can be customized by changing the value in the `if(distanceCm < 40)` statement within the code.

