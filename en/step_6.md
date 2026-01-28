## Program the relay and pump

--- task ---

Add the `picozero` class you need to control the relay.

--- code ---
---
language: python
filename: touchfree_tap.py
line_numbers: true
line_number_start: 1
line_highlights: 1
---
from picozero import DistanceSensor, DigitalOutputDevice    # import digital device class too
from time import sleep                        # import delay function

sensor = DistanceSensor(echo=14, trigger=15)  # initialise sensor on GP14 and 15

while True:                                   # repeat forever
    d = sensor.distance                       # set 'd' to sensor measurement value
    print(round(d, 2), "m")     # show distance in metres
    sleep(0.5)                                # short pause
--- /code ---

--- /task ---

--- task ---

Add a line to set up the `relay` on **GP**`28`:

--- code ---
---
language: python
filename: touchfree_tap.py
line_numbers: true
line_number_start: 1
line_highlights: 4
---
from picozero import DistanceSensor, DigitalOutputDevice
from time import sleep

relay = DigitalOutputDevice(28, active_high=True)   # initialise relay on GP28
sensor = DistanceSensor(echo=14, trigger=15)        # initialise sensor on GP14 and 15

--- /code ---

--- /task ---

--- task ---

Add an `if` statement inside the `while True` loop to check how far away your hand is.

In this example, **if** something is closer to the sensor than 12cm, **then** the relay (and pump) turns on. **Else**, the relay turns off again.

--- code ---
---
language: python
filename: touchfree_tap.py
line_numbers: true
line_number_start: 7
line_highlights: 11-14, 16
---
while True:                                  # repeat forever
    d = sensor.distance                      # set 'd' to sensor measurement value
    print("Distance:", round(d, 2), "m")     # show distance in metres

    if d < 0.12:           # hand is within 12cm - adjust this number to change the activation distance
        relay.on()         # turn on the pump
    else:
        relay.off()        # turn off the pump

    sleep(0.5)             # short pause
--- /code ---

--- /task ---

--- task ---
Click on **Run** and test your touch-free tap:  
- Hold your hand within **12cm**. The relay should click and turn the pump on.
- Move your hand away so that the relay releases and the pump turns off.

<video controls width="480">
  <source src="images/touch-free-tap_demo.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
--- /task ---