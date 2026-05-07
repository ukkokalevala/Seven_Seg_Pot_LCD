Project Overview: Potentiometer-Controlled 7-Segment Display with LCD Feedback
Purpose
An interactive system that allows users to selectively illuminate individual segments of a 7-segment display by rotating a potentiometer, while simultaneously displaying segment information on an LCD screen.

Hardware Components
Arduino board (Uno/Nano/Mega compatible)

16×2 I2C LCD display (address 0x27)

7-segment display (common cathode configuration)

10kΩ potentiometer

Current-limiting resistors (220-330Ω for each segment)

Breadboard and jumper wires

Pin Connections
Component	Arduino Pins
LCD (I2C)	SDA (A4), SCL (A5)
Segment A	Pin 2
Segment B	Pin 3
Segment C	Pin 4
Segment D	Pin 5
Segment E	Pin 6
Segment F	Pin 7
Segment G	Pin 8
Common Pin	Pin 9 (GND for common cathode)
Potentiometer	A0
How It Works
Input Reading: Reads analog value from potentiometer (0-1023)

Value Mapping: Maps the potentiometer value to segment indices 0-6

Segment Control: Turns on the selected segment while turning others off

LCD Display: Shows current segment number and its binary code pattern

Segment Index Mapping
0 → Segment A (top horizontal)

1 → Segment B (top-right vertical)

2 → Segment C (bottom-right vertical)

3 → Segment D (bottom horizontal)

4 → Segment E (bottom-left vertical)

5 → Segment F (top-left vertical)

6 → Segment G (middle horizontal)

Binary Code Reference Table
Each segment has a 7-bit binary code (MSB to LSB: A→G):

A: 1000000 (only segment A illuminated)

B: 0100000 (only segment B illuminated)

C: 0010000 (only segment C illuminated)

D: 0001000 (only segment D illuminated)

E: 0000100 (only segment E illuminated)

F: 0000010 (only segment F illuminated)

G: 0000001 (only segment G illuminated)

Key Functions
setup(): Initializes LCD, sets pin modes, clears segments

loop(): Continuously reads potentiometer and updates display

displaySegment(index): Controls which segment illuminates

displayBinaryCode(index): Shows segment info on LCD

clearSegments(): Turns off all segments

Educational Value
This project demonstrates:

Analog input reading and mapping

Digital output control

I2C communication with LCD displays

7-segment display multiplexing concepts

Real-time data visualization

Binary representation of display states

Potential Enhancements
Display actual segment patterns (not just binary strings)

Add button to toggle between segment selection modes

Implement digit display (0-9) instead of individual segments

Add brightness control via PWM

Include serial monitoring for debugging

Create a "segment test" sequence for troubleshooting

Troubleshooting Notes
Verify LCD I2C address (use I2C scanner if 0x27 doesn't work)

For common anode displays, change commonPin to HIGH and invert segment logic

Add current-limiting resistors to prevent LED damage

Ensure potentiometer is wired correctly (outer pins to 5V/GND, wiper to A0)

This project serves as an excellent learning tool for understanding display technologies, analog-to-digital conversion, and real-time system control with Arduino.

