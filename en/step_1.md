## What you will make

Build a **Touchless Water Faucet** that uses a Raspberry Pi Pico, the `picozero` library, an ultrasonic sensor, a relay, and a 5-12 V DC submersible pump. When hands are detected within a set distance, the relay opens the valve; when hands move away, it closes.

<video controls width="480">
  <source src="images/wywm.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

### You will need:
- **Raspberry Pi Pico** — microcontroller for running the system
- **Ultrasonic Distance Sensor (HC-SR04)** — detects hand distance for touchless control
- **5 V Single-Channel Relay Module** — electrically isolates and switches the pump on/off  
- **Mini DC Water Pump Module (5–12 V)** — substitutes for a solenoid valve to control water flow
- **External DC Supply (5–12 V)** — to power the water pump  
- **USB Power (5 V)** — to power the Pico
- **Breadboard and jumper wires** — for temporary circuit assembly
- **2 resistors (1 kΩ and 470 Ω)** — for the ECHO pin voltage divider
- **Housing or mount** — fabricated from recycled materials, or with a 3D printer

To program the Raspberry Pi Pico, you will need the [Thonny IDE](http://thonny.org/){:target="_blank"} and MicroPython packages installed. 

[Instructions for this process are available here.](https://projects.raspberrypi.org/en/projects/getting-started-with-the-pico/2){:target="_blank"} 




