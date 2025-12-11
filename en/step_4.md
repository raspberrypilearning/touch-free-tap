## Measure distance with PicoZero

To program the Raspberry Pi Pico, you will need the [Thonny IDE](http://thonny.org/){:target="_blank"} and MicroPython packages installed. [Instructions for this process are available here.](https://projects.raspberrypi.org/en/projects/getting-started-with-the-pico/2){:target="_blank"}   

--- task ---
Open Thonny and create a new file called `tank_sensor.py`.
--- /task ---

--- task ---
Add code to measure distance using the ultrasonic sensor.

--- code ---
---
language: python
filename: tank_sensor.py
line_numbers: true
---

from picozero import DistanceSensor     # import sensor class
from time import sleep                  # import delay function

sensor = DistanceSensor(echo=14, trigger=15)  # initialise sensor on GP 14 & 15

while True:                                   # repeat forever
    d = sensor.distance                       # set 'd' to sensor measurement value 
    print(round(d, 2), "m")                   # show distance in metres
    sleep(0.5)                                # short pause

--- /code ---

--- /task ---

--- task ---
Click **Run**.  
Move your hand below the sensor — the distance values should change.

--- collapse ---

---

title: TypeError -  can't convert NoneType to float

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


![](images/UDS_distance.gif)

--- /task ---


