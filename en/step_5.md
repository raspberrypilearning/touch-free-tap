## Wire the relay and pump

--- task ---

Connect the `IN` pin on the relay to `GP15` on the Pico.
This will act as the pump control signal.

{:width="300px"}

--- /task ---

--- task ---

Connect `VCC` to the 5V rail on the breadboard.
This will provide the 5V of power the relay needs to run the pump.

{:width="300px"}

--- /task ---

--- task ---

Connect `GND` to the `GND` rail on the breadboard.
The relay coil now shares power with the sensor but remains isolated from the pump circuit.

{:width="300px"}

--- /task ---

### Connect the Mini DC Water Pump

--- task ---

Attach the pump + wire to the positive terminal of your external 5–12 V DC supply.

{:width="300px"}

--- /task ---

--- task ---

Connect the pump – wire to the `COM` (Common) terminal on the relay.
{:width="300px"}

--- /task ---

--- task ---

Then connect the `NO` (Normally Open) terminal to the negative terminal of the DC supply.


{:width="300px"}

--- /task ---

When the relay is triggered by the Pico, it will close the circuit and power the pump.
This keeps the Pico safely isolated from the pump’s higher-current circuit.