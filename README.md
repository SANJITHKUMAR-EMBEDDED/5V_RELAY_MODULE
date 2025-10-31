Project #2: 5V Relay Module

This is Project 2 of my #50BoardChallenge. It's a 5V relay module designed to safely control high-voltage AC appliances (like a lamp or fan) using a simple 5V logic signal from a microcontroller.

## Features
* Controls 230V AC loads with a 5V logic signal.
* Uses a standard `SRD-05VDC-SL-C` 5V relay.
* Includes a `BC547` transistor to drive the relay coil, so the microcontroller pin is protected.
* **Flyback Diode** (`1N4007`) implemented to protect the transistor from voltage spikes.
* **Indicator LEDs:** A "Power" LED and a "Status" LED to show when the relay is active.
* Uses a 3-pin screw terminal for safe, secure high-voltage connections.

## Professional Design Rules
This board's main challenge was **safety and isolation**. I designed it by separating the 230V AC side from the 5V logic side.

* **Isolation:** Created two distinct "Net Classes" in KiCad:
    * **`HighVoltage`:** Set with a large **80 mil Clearance** and **60 mil Traces** for the 230V AC path.
    * **`POWER`:** Set with **20 mil Traces** for the 5V logic power.
* **Solid `GND` Plane:** Used a solid copper pour on the bottom layer for the low-voltage `GND` net, acting as a stable, low-noise return path.
* **Physical Separation:** The PCB layout keeps all high-voltage components on one side and all low-voltage components on the other to prevent arcing.
* **DRC:** The final design passed all Design Rules Checks with **0 errors and 0 warnings**.
