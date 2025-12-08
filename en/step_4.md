## Read distance with PicoZero

To program the Raspberry Pi Pico, you will need the [Thonny IDE](http://thonny.org/){:target="_blank"} and MicroPython packages installed. [Instructions for this process are available here.](https://projects.raspberrypi.org/en/projects/getting-started-with-the-pico/2){:target="_blank"}  

--- task ---
Open Thonny and create a new file called `touchless_tap.py`.
--- /task ---

--- task ---

Add code to measure distance using the ultrasonic sensor and print out the result:

--- code ---
---
language: python
filename: touchless_tap.py
line_numbers: true
---

from picozero import DistanceSensor
from time import sleep

sensor = DistanceSensor(echo=2, trigger=3)

while True:
    d = sensor.distance
    print("Distance:", round(d, 2), "m")
    sleep(0.2)
--- /code ---

--- /task ---

--- task ---
Click **Run**.  
Move your hand in front of the sensor — the distance values should change.

![A clip showing a hand moving closer and further from an ultrasonic distance sensr while the numbers on the readout change](images/UDS_distance.gif)

--- collapse ---

---

title: TypeError - can't convert NoneType to float

---

Tip: If you see the error `TypeError: can't convert NoneType to float`

This usually means the distance sensor did not give a proper reading.
The most common cause is a loose connection, but it could be something else stopping the sensor from working.

Check these things:

- Check that no jumper wires are loose or leaning in the breadboard/circuit.
- Make sure the sensor is facing an object that is not too close (2cm) or too far away (4m).
- Check your voltage divider resistors are properly connected
- Do you have the right `trigger` and `echo` pins set?

--- /collapse ---

--- /task ---