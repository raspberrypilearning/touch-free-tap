## Program the relay and pump

--- task ---

Add the `picozero` class needed to control the relay:

--- code ---
---
language: python
filename: touchless_tap.py
line_numbers: true
line_number_start: 1
line_highlights: 1
---
from picozero import DistanceSensor, DigitalOutputDevice    # import digital device class too
from time import sleep                  # import delay function

sensor = DistanceSensor(echo=14, trigger=15)  # initialise sensor on GP 14 & 15

while True:                                  # repeat forever
    print(round(sensor.distance, 2), "m")     # show distance in metres
    sleep(0.5)                                # short pause
--- /code ---

--- /task ---

--- task ---

Add a line to set up the `relay` on `GP 28`:

--- code ---
---
language: python
filename: touchless_tap.py
line_numbers: true
line_number_start: 1
line_highlights: 4
---
from picozero import DistanceSensor, DigitalOutputDevice
from time import sleep

relay = DigitalOutputDevice(28, active_high=True) # initialise relay on GP 28
sensor = DistanceSensor(echo=14, trigger=15)  # initialise sensor on GP 14 & 15

--- /code ---

--- /task ---

--- task ---

Add an `if` statement inside the `while True` loop to check how far away your hand is.  

In this example; **if** something is closer to the sensor than 12 cm, **then** the relay (and pump) turns on. 
**Else**, the relay turns off again.

--- code ---
---
language: python
filename: touchless_tap.py
line_numbers: true
line_number_start: 7
line_highlights: 11-14, 16
---
while True:
    d = sensor.distance
    print("Distance:", round(d, 2), "m")

    if d < 0.12:           # Hand is within 12 cm - adjust this number to change activation distance
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

<video controls width="480">
  <source src="images/touch-free-tap_demo.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
--- /task ---