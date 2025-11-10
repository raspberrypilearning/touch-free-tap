## Program the relay and sensor

--- task ---
Extend your working distance test code from Step 4 by adding the relay logic.

Start with your existing script:

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 1
line_highlights: 1-6
---
from picozero import DistanceSensor
from time import sleep

ultra = DistanceSensor(trigger=3, echo=2, max_distance=1.5)  # metres

while True:
    d = ultra.distance
    print("Distance:", round(d, 3), "m")
    sleep(0.2)
--- /code ---

--- /task ---

--- task ---
Import the extra library needed for controlling the relay and add it **above** your existing code.

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 1
line_highlights: 1,4
---
from picozero import DistanceSensor, DigitalOutputDevice  # Added relay control
from time import sleep, time                              # Added time for tracking open state
--- /code ---

--- /task ---

--- task ---
Next, create a relay output and some variables **after** the `ultra` setup but before the loop.

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 7
line_highlights: 8-13
---
ultra = DistanceSensor(trigger=3, echo=2, max_distance=1.5)  # metres
valve = DigitalOutputDevice(15, active_high=False, initial_value=False)  # Relay on GP15

HAND_ON  = 0.10   # 10 cm to open
HAND_OFF = 0.14   # 14 cm to close
MIN_OPEN = 0.4    # seconds; avoid rapid cycling

open_since = 0.0
is_open = False
--- /code ---

--- /task ---

--- task ---
Now replace your simple print loop with logic that switches the relay on and off depending on the distance.

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 15
line_highlights: 18-31
---
while True:
    d = ultra.distance
    if d is not None:
        if (not is_open) and (d < HAND_ON):
            valve.on()              # Open the valve
            is_open = True
            open_since = time()
        elif is_open and (d > HAND_OFF) and (time() - open_since >= MIN_OPEN):
            valve.off()             # Close the valve
            is_open = False

    # Optional feedback
    print("Distance:", round(d, 3), "m", "Valve:", "ON" if is_open else "OFF")
    sleep(0.1)
--- /code ---

--- /task ---

--- task ---
Click **Run** and test your tap:
- Place your hand within 10 cm → valve turns on.
- Move your hand away → valve turns off once past 14 cm and after the delay.
- Watch the distance and valve state print in the Shell.
--- /task ---