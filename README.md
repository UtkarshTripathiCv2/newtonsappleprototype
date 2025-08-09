# newtonsappleprototype

Arduino Freefall Height Calculator
This project uses an Arduino and an MPU6050 accelerometer to measure the duration of a freefall and calculate the height of the drop. It's a simple and effective way to see physics in action.

How It Works
The device uses an accelerometer to determine its state. Here's the operational flow:

Arming: The device is "armed" when you remove your finger from a capacitive touch sensor. An onboard LED will light up to indicate it's ready.

Freefall Detection: The MPU6050 continuously measures acceleration. When the device is dropped, the total acceleration drops to nearly zero. The code registers this as the start of a freefall and begins timing.

Impact Detection: When the device hits the ground, it experiences a sudden spike in acceleration. The code detects this impact as the end of the freefall and stops the timer.

Calculation: Using the recorded fall time (t), the height (h) is calculated with the standard kinematic equation: h=
frac12gt 
2
 , where g is the acceleration due to gravity (9.8m/s 
2
 ).

Display Results: The total fall time and the calculated height in meters are printed to the Serial Monitor. The LED turns off, and the device is ready for another drop.

Hardware Required
An Arduino board (like the Uno or Nano)

MPU6050 6-axis Accelerometer/Gyroscope module

TTP223 Capacitive Touch Sensor module

A standard LED

Breadboard and jumper wires

Wiring
Connect the components as follows:

Component	Arduino Pin
TTP Sensor (Signal Pin)	Digital Pin 13
LED (Anode/Long leg)	Digital Pin 12
MPU6050 (SDA)	A4 (SDA)
MPU6050 (SCL)	A5 (SCL)
MPU6050 (VCC)	5V
MPU6050 (GND)	GND
TTP Sensor (VCC)	5V
TTP Sensor (GND)	GND



Setup and Usage
Wire the components according to the table above.

Upload the provided code to your Arduino board.

Open the Arduino IDE's Serial Monitor and set the baud rate to 9600.

Touch and hold your finger on the TTP sensor. The device is now idle.

To arm the device, simply remove your finger. The LED will turn on.

Drop the device onto a safe surface.

Check the Serial Monitor for the results!
