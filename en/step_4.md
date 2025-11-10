## Read distance with `picozero`

Verify reliable ranging before touching the relay.

```python
# main.py
from picozero import DistanceSensor
from time import sleep

ultra = DistanceSensor(trigger=3, echo=2, max_distance=1.5)  # metres

while True:
    d = ultra.distance   # metres (float)
    if d is not None:
        print("Distance:", round(d, 3), "m")
    else:
        print("Out of range")
    sleep(0.2)
```

**Test:** Move a hand towards the sensor and confirm readings drop smoothly to ~0.06–0.12 m in your setup.
