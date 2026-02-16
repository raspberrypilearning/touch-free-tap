## Measure distance with picozero

To program the Raspberry Pi Pico, you will need the [Thonny IDE](http://thonny.org/){:target="_blank"}, and MicroPython must be installed on your Raspberry Pi Pico. You can find [instructions to help you set up here](https://projects.raspberrypi.org/en/projects/getting-started-with-the-pico/2){:target="_blank"}.

--- task ---
Open Thonny and create a new file called `touchfree_tap.py`.
--- /task ---

--- task ---
Add code to measure distance using the ultrasonic sensor.

--- code ---
---
language: python
filename: touchfree_tap.py
line_numbers: true
---

from picozero import DistanceSensor     # import sensor class
from time import sleep                  # import delay function

sensor = DistanceSensor(echo=14, trigger=15)  # initialise sensor on GP14 and 15

while True:                                   # repeat forever
    d = sensor.distance                       # set 'd' to sensor measurement value 
    print(round(d, 2), "m")                   # show distance in metres
    sleep(0.5)                                # short pause

--- /code ---

--- /task ---

--- task ---
Click on **Run**.

Move your hand below the sensor. The distance values should change.

--- collapse ---

---

title: "TypeError: can't convert NoneType to float"

---

If you see the error `TypeError: can't convert NoneType to float`, this usually means the distance sensor has not given a proper reading. The most common cause is a loose connection, but something else could be stopping the sensor from working.

Check that:

- No jumper wires are loose or leaning in the breadboard or circuit
- The sensor is facing an object that is not too close (2cm) or too far away (4m)
- Your voltage divider resistors are connected properly
- You have set the correct `trigger` and `echo` pins

--- /collapse ---


![Moving a hand to test the distance sensor, and distance values showing in Thonny.](images/UDS_distance.gif)

--- /task ---


