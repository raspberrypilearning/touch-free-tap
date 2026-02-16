## What you will make

Build a **touch-free tap** with a Raspberry Pi Pico, an ultrasonic sensor, a relay, and a 5-12V DC submersible pump. When hands are detected within a set distance, the relay will open the valve; when hands move away, it will close.

<video controls width="480">
  <source src="images/wywm.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

### You will need:
- **Raspberry Pi Pico** — microcontroller for running the system
- **USB power supply (5V)** — to power the Raspberry Pi Pico
- **Ultrasonic distance sensor (HC-SR04)** — to detect hand distance, for touchless control
- **5V single-channel relay module** — to electrically isolate and turn the pump on and off
- **Mini DC water pump module (5–12V)** — to substitute for a solenoid valve to control water flow
- **External DC power supply (5–12V)** — to power the water pump
- **Breadboard and jumper wires** — for assembling the circuit
- **1kΩ resistor and 2kΩ resistor** — for the **ECHO** pin voltage divider
- **Barrel, bucket, or small tank of water**
- **Housing or mount** — made from recycled materials or with a 3D printer
- **Plastic tubing**

To program the Raspberry Pi Pico, you will also need the [Thonny IDE](http://thonny.org/){:target="_blank"}, and MicroPython must be installed on your Raspberry Pi Pico. You can find [instructions to help you set up here](https://projects.raspberrypi.org/en/projects/getting-started-with-the-pico/2){:target="_blank"}. 