## Wire the sensor circuit

Connect the sensor to the Raspberry Pi Pico. Use a divider to keep **ECHO** at 3.3V logic.

--- task ---
 
Set your Raspberry Pi Pico securely on a breadboard or workspace so that you can easily access all the pins for wiring.

![A Raspberry Pi Pico H mounted into a breadboard, aligned with the top row.](images/pico_breadboard.png){:width="300px"} 

--- /task ---

--- task ---

Connect the **VBUS** pin to the power rail on the edge of your breadboard, and any **GND** pin to the ground rail on your breadboard. This will allow multiple devices to use the power from your power supply. 
![The Raspberry Pi Pico H on the breadboard connected to the power and ground rails with jumper wires.](images/touchless_faucet_0.png){:width="300px"}

--- /task ---

--- task ---
Connect the **VCC** pin on the ultrasonic sensor to the power rail on the breadboard, and the **GND** pin to the ground rail. This will give the sensor power to operate.(Note that this configuration of wires will allow for resistors in later tasks.)

![The HC-SR04 ultrasonic sensor has been connected to the power and ground rails with jumper wires as described.](images/touchless_faucet_1.png){:width="300px"}
--- /task ---

--- task ---
Use a jumper wire to connect the **TRIG** pin on the sensor to **GP3** on the Raspberry Pi Pico. This pin will send the signal that will start a distance measurement.
![The TRIG pin on the sensor has been connected to GP3 on the Raspberry Pi Pico with a jumper wire.](images/touchless_faucet_2.png){:width="300px"}
--- /task ---

--- task ---
To protect the Raspberry Pi Pico's input pin from the 5V circuit, make a voltage divider on the **ECHO** line.

First, connect a 1kΩ resistor between the **ECHO** pin on the sensor and **GP2** on the Raspberry Pi Pico.
![A resistor has been connected between the ECHO pin and GP2 with a jumper wire.](images/touchless_faucet_3.png){:width="300px"}
--- /task ---

--- task ---
Next, connect a 2kΩ resistor between the **ECHO** pin and ground on the breadboard. This will lower the signal to a safe level (about 3.3V) for the Raspberry Pi Pico's input.
![A resistor has been added between the ECHO pin and ground.](images/touchless_faucet_4.png){:width="300px"}
--- /task ---

--- task ---
Double-check your connections:

- The 1kΩ resistor should run from **ECHO** to **GP2**
- The 2kΩ resistor should run from **ECHO** to ground
- There should be no loose wires or crossed connections

--- /task ---