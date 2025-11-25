## Wire the relay and pump

Wire the relay and pump circuit that lets the Raspberry Pi Pico safely turn a water pump on and off.

The relay works like a switch that keeps the Pico separate from the pump’s bigger power supply. When the Pico sends a signal, the relay connects the pump with the larger power supply and the pump starts running.

--- task ---

Connect the `IN` pin on the relay to `GP15` on the Pico.
This will act as the pump control signal.

![Raspberry Pi Pico H connected to HC-SR04 sensor and blue relay module using multiple coloured jumper wires.](images/touchless_faucet_5.png){:width="600px"}

--- /task ---

--- task ---

Connect `VCC` to the 5V rail on the breadboard and the `GND` to the `GND` rail on the breadboard..
The relay coil now shares power with the sensor.

![Raspberry Pi Pico H connected to HC-SR04 sensor and relay module with black ground wire added.](images/touchless_faucet_6.png){:width="600px"}

--- /task ---

### Connect the Mini DC Water Pump

--- task ---

Attach the pump's `+` (red) wire to the positive terminal of your external 5–12 V DC supply (also probably a red wire).

![Raspberry Pi Pico H circuit with HC-SR04, relay, motor, and AAA battery pack connected by red and black wires.](images/touchless_faucet_7.png){:width="800px"}

--- /task ---

--- task ---

Connect the pump's `–` (black) wire to the `COM` (Common) terminal on the relay.
![Raspberry Pi Pico H circuit with HC-SR04, relay, motor, and battery pack wired via grey jumper to relay output.](images/touchless_faucet_8.png){:width="800px"}

--- /task ---

--- task ---

Then connect the `NO` (Normally Open) terminal to the negative terminal of the DC supply (probably a black wire).


![Completed circuit of Raspberry Pi Pico H, HC-SR04 sensor, relay, motor, and AAA battery pack on breadboard.](images/touchless_faucet_9.png){:width="800px"}

--- /task ---

When the relay is triggered by the Pico, it will close the circuit and power the pump.
This keeps the Pico safely isolated from the pump’s higher-current circuit.

**Important:** Don't run your pump outside of water for too long, or it will heat up and may get damaged!