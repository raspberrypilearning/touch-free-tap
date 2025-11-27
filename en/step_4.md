## Program the Sensor

To program the Raspberry Pi Pico, you will need the [Thonny IDE](http://thonny.org/){:target="_blank"} and MicroPython packages installed. 

[Instructions for this process are available here.](https://learning-admin.raspberrypi.org/en/projects/getting-started-with-the-pico/2){:target="_blank"}  

--- task ---
Open Thonny and create a new file called `touchless_tap.py`.
--- /task ---

--- task ---
Add code to measure distance using the ultrasonic sensor.

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
Move your hand above the sensor — the distance values should change.
--- /task ---