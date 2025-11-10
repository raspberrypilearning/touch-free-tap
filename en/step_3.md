## Wire the circuit

Connect the sensor and relay to the Pico. Keep Echo at 3.3 V logic with a divider.

--- task ---
Place the Pico on a breadboard. Power rails: 5 V for HC-SR04 and relay, 3.3 V logic for the Pico. Tie all **grounds** together.
--- /task ---

--- task ---
**Ultrasonic sensor**  
VCC → 5 V; GND → GND; TRIG → GP3; ECHO → GP2 through a divider: Echo pin → 1 kΩ → GP2 and Echo pin → 470 Ω → GND.
--- /task ---

--- task ---
**Relay module**  
IN → GP15; VCC → 5 V; GND → GND.
--- /task ---

--- task ---
**Solenoid valve**  
12 V + → Valve +; Valve − → Relay **COM**; Relay **NO** → 12 V −. Verify the relay isolates the 12 V loop from the Pico.
--- /task ---

--- task ---
Continuity checks: no shorts; Echo divider values correct; common ground confirmed.
--- /task ---
