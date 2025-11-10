## Program the relay and sensor

--- task ---
Add the libraries needed to access the Pico’s distance and timing functions.

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 1
line_highlights: 1-2
---
from picozero import DistanceSensor, DigitalOutputDevice
from time import sleep, time
--- /code ---

--- /task ---

--- task ---
Set up the Pico to read distance from the ultrasonic sensor and control a relay connected to **Pin 15**.

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 4
line_highlights: 4-6
---
ultra = DistanceSensor(trigger=3, echo=2, max_distance=1.5)
valve = DigitalOutputDevice(15, active_high=False, initial_value=False)
--- /code ---

--- /task ---

--- task ---
Define the threshold and timing variables that will determine when the valve opens and closes.

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 7
line_highlights: 7-9
---
HAND_ON  = 0.10   # 10 cm to open
HAND_OFF = 0.14   # 14 cm to close
MIN_OPEN = 0.4    # seconds; avoid rapid cycling
--- /code ---

--- /task ---

--- task ---
Create variables to track the current valve state and when it was last opened.

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 11
line_highlights: 11-12
---
open_since = 0.0
is_open = False
--- /code ---

--- /task ---

--- task ---
Write the loop to read distance and switch the relay on and off using hysteresis, preventing rapid flicker.

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 14
line_highlights: 15-26
---
while True:
    d = ultra.distance
    if d is not None:
        if (not is_open) and (d < HAND_ON):
            valve.on()
            is_open = True
            open_since = time()
        elif is_open and (d > HAND_OFF) and (time() - open_since >= MIN_OPEN):
            valve.off()
            is_open = False
    sleep(0.05)
--- /code ---

--- /task ---

--- task ---
Click **Run** and test the tap behaviour:
- Place your hand within 10 cm → valve opens.
- Move your hand away → valve closes once past 14 cm and after `MIN_OPEN` time.
--- /task ---
