## Program the relay and pump

--- task ---
Add the libraries needed to access the Pico’s distance sensor and control the relay.

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 1
line_highlights: 1-3
---
from picozero import DistanceSensor, DigitalOutputDevice
from time import sleep
--- /code ---

--- /task ---

--- task ---
Set up the relay and ultrasonic sensor.  The relay will turn on when a hand is within 12 cm of the sensor.

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 4
line_highlights: 4-7
---
valve = DigitalOutputDevice(15, active_high=False)

ultra = DistanceSensor(trigger=3, echo=2, max_distance=1.5, threshold_distance=0.12)
--- /code ---

--- /task ---

--- task ---
Tell the Pico what to do when a hand is detected and when it moves away.

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 8
line_highlights: 8-10
---
ultra.when_in_range = lambda: valve.on()
ultra.when_out_of_range = lambda: valve.off()
--- /code ---

--- /task ---

--- task ---
Keep the program running so it can respond to sensor changes.

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 11
line_highlights: 11-13
---
while True:
    sleep(1)
--- /code ---

--- /task ---

--- task ---
Click **Run** and test your tap:
- Place your hand within 12 cm → the valve opens.
- Move your hand away → the valve closes.
--- /task ---
