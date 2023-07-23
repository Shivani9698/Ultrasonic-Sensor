# Ultrasonic-Sensor(HC-SR04)

# Ultrasonic Distance Measurement Arduino Sketch

This repository contains an Arduino sketch that allows you to measure distances using an ultrasonic sensor and display the results in both centimeters and inches.

## Hardware Requirements

To use this Arduino sketch, you will need the following components:

1. Arduino board (e.g., Arduino Uno)
2. Ultrasonic sensor (e.g., HC-SR04)
3. Jumper wires to connect the sensor to the Arduino

## Circuit Connection

Connect the ultrasonic sensor to the Arduino board as follows:

- *VCC (Sensor)* to *5V (Arduino)*
- *GND (Sensor)* to *GND (Arduino)*
- *TRIG (Sensor)* to *Digital Pin 5 (Arduino)*
- *ECHO (Sensor)* to *Digital Pin 18 (Arduino)*
  
## Wiring diagram

![image](https://github.com/Shivani9698/Ultrasonic-Sensor/assets/119753029/e33c3987-46c0-40b7-a9c7-84bd9d50c01f)

## How the Sketch Works

The Arduino sketch uses the HC-SR04 ultrasonic sensor to measure distances. Here's a brief overview of how the sketch works:

1. The trigger pin (TRIG) of the sensor is connected to Digital Pin 5 on the Arduino, and the echo pin (ECHO) is connected to Digital Pin 18.
2. In the `setup()` function, the serial communication is initialized at a baud rate of 115200, and the pin modes for TRIG and ECHO are set (TRIG as OUTPUT and ECHO as INPUT).
3. In the `loop()` function, the following steps are performed:
   - A short pulse of 10 microseconds is sent to the TRIG pin to trigger the ultrasonic sensor.
   - The duration of the echo signal is measured using the `pulseIn()` function, which returns the time in microseconds it takes for the echo signal to return.
   - The distance is calculated in centimeters using the formula: `distance = duration * speed of sound / 2`. The speed of sound is set to 0.034 cm/microsecond in the `SOUND_SPEED` constant.
   - The calculated distance in centimeters is then converted to inches using the conversion factor defined in the `CM_TO_INCH` constant.
   - The measured distance in centimeters and inches is printed to the Serial Monitor for display.
   - The loop waits for 1 second using the `delay()` function before taking the next distance reading.

## How to Use

To use this Arduino sketch:

1. Connect the ultrasonic sensor to the Arduino board following the circuit connection mentioned above.
2. Open the Arduino IDE and upload the sketch to your Arduino board.
3. Open the Serial Monitor in the Arduino IDE (set the baud rate to 115200) to view the distance measurements in centimeters and inches.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- The sketch is based on the HC-SR04 Ultrasonic Sensor Library example provided in the Arduino IDE.
- HC-SR04 Ultrasonic Sensor Library: [https://github.com/filipeflop/Ultrasonic](https://github.com/filipeflop/Ultrasonic)

---

