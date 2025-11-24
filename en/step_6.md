## Program the relay and pump

--- task ---

Add the libraries needed to access the Pico’s distance sensor and control the relay.

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 1
line_highlights: 1
---
from picozero import DistanceSensor, DigitalOutputDevice
from time import sleep

sensor = DistanceSensor(echo=2, trigger=3, max_distance=1)

while True:
    d = sensor.distance
    print("Distance:", round(d, 2), "m")
    sleep(0.5)
--- /code ---

--- /task ---

--- task ---

Add a line to set up the **relay on Pin 15**:

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 1
line_highlights: 4
---
from picozero import DistanceSensor, DigitalOutputDevice
from time import sleep

relay = DigitalOutputDevice(15, active_high=False)
sensor = DistanceSensor(echo=2, trigger=3)

--- /code ---

--- /task ---

--- task ---

Add an `if` statement inside the `while True` loop to check how far away your hand is.  

In this example; if it’s closer than 12 cm, the relay (and pump) turns on. When it’s further away, the relay turns off again.

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 7
line_highlights: 11-14, 16
---
while True:
    d = sensor.distance
    print("Distance:", round(d, 2), "m")

    if d < 0.12:           # Hand is within 12 cm
        relay.on()         # Turn on the pump
    else:
        relay.off()        # Turn off the pump

    sleep(0.2)
--- /code ---

--- /task ---

--- task ---
Click **Run** and test your touchless faucet:  
- Place your hand within **12 cm** → the relay should click and turn the pump on.  
- Move your hand away so the relay releases and the pump turns off.  
--- /task ---