## Mount the distance sensor

Create a small, splash-resistant mount so that the ultrasonic sensor faces downwards and ignores stray reflections.

--- task ---
Cut a small piece of plastic or print a bracket that can hold the ultrasonic sensor level, and add a short 'hood' so that any water splashes do not hit the sensor. Make sure that the bracket will keep the sensor at least 6–8cm above the expected water level.
--- /task ---

--- task ---
Mark and drill two holes in the bracket so that you can use screws or zip ties to secure the sensor.
--- /task ---

--- task ---
Securely attach the bracket to a safe stand or mock basin. Make sure that no conductive parts could short the Raspberry Pi Pico or relay.
--- /task ---

This example uses recycled plastic containers, cardboard, and a bucket as a simple prototype:

![A labelled diagram of a bucket of water with a sensor-controlled tap. The tap is made of a milk bottle handle and is positioned on the rim of the bucket. The sensor is attached to a cardboard hood and is positioned above the tap. The sensor is connected to a Raspberry Pi Pico in a breadboard, and the circuit also includes a relay and power supply. These components are held in a plastic tray secured across the top of the bucket. A DC pump is in the water and is connected to the circuit and a plastic tube that leads to the tap.](images/bucket-tap-diagram.png)