## Extensions and challenges

--- task ---
Add an **LED status** indicator on GP14 that lights when the valve is open.  

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 1
line_highlights: 1-3
---
from picozero import LED

led = LED(14)
--- /code ---

Update your main loop to mirror the valve’s state:

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 15
line_highlights: 22-23
---
        if (not is_open) and (d < HAND_ON):
            valve.on()
            led.on()              # LED on when valve open
            is_open = True
            open_since = time()
        elif is_open and (d > HAND_OFF) and (time() - open_since >= MIN_OPEN):
            valve.off()
            led.off()             # LED off when valve closed
            is_open = False
--- /code ---
--- /task ---

--- task ---
Add a **buzzer** to sound if the valve stays open for more than 15 seconds.  
This helps detect possible sensor errors or water wastage.

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 25
line_highlights: 26-31
---
from picozero import Buzzer

buzzer = Buzzer(13)

if is_open and (time() - open_since > 15):
    buzzer.on()
else:
    buzzer.off()
--- /code ---
--- /task ---

--- task ---
Add a **flow sensor** to count litres dispensed and print the total volume to the Shell every minute.  
You can expand this later to log data to a CSV file for sustainability tracking.
--- /task ---

--- task ---
Optional upgrade: Connect to an **IoT service** (e.g., Blynk or ThingSpeak) to upload valve activity or flow data.  
This demonstrates environmental data logging and analysis.
--- /task ---

--- task ---
Challenge: Add a **day/night mode** using an LDR sensor so the tap system powers down at night to save energy.
--- /task ---