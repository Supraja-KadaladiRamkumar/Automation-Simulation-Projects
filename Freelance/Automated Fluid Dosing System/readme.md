This project implements a state-based PLC control system for an automated fluid saturation process. The system manages fluid mixing, priming sequences, object passage counting and automated top-up dosing cycles to maintain consistent pad saturation.

**Process Flow**

_1. Standby Mode_

* System initialises with all outputs off and passage count held at zero.
* Remains in standby until the System Enable Switch is activated.

_2. Initial Priming Sequence_  

* Triggered on rising edge of System Enable Switch.
* Opens the Base Fluid Solenoid Valve for the configured priming duration.
* Runs the Additive Dosing Pump simultaneously for its configured priming duration.
* Transitions to Normal Operation once both timers complete.

_3. Normal Operation_

* Monitors the Passage Sensor and increments the passage counter on each detection.
* Triggers a top-up dosing cycle when the counter reaches the configured target.
* Resets the counter and resumes counting after each completed top-up cycle.

_4. Alarm Handling_

* Activates on Additive Low Level Sensor detection during Normal Operation.
* Disables top-up cycles and flashes the Alarm Light at 3 second intervals.
* Stores elapsed timer values to allow cycle resumption without restart after alarm reset.
* Clears on Manual Reset Button press once the low level sensor is no longer active.

_5. Maintenance Mode_

* Activated via manual jog buttons for the solenoid valve and dosing pump independently.
* Suspends priming and top-up timers during maintenance activity.

**Control Logic**

* Core program written in Structured Text (ST).
* State-based sequencing:
  - State 0: Standby
  - State 1: Priming
  - State 2: Normal Operation
  - State 3: Alarm
* Maintenance mode runs independently and suspends timer logic when active.
* Alarm state stores timer offsets to allow seamless cycle resumption after reset.
* Tank level visualisation scales dynamically based on elapsed timer values.

**HMI Design**

* Built in CODESYS Visualisation.
* Toggle switches simulate physical inputs:
  - System Enable Switch
  - Passage Sensor
  - Additive Level Sensor
  - Manual Reset Button
  - Valve and Pump Jog Buttons
* Display only parameters: Current Passage Count, Elapsed Timer values, Tank levels.
* Modifiable parameters: Target Passage Count, Priming and Top-Up Timer presets.

**Tools Used**

_Platform:_ CODESYS V3.5 SP20 Patch 3

_Language:_ Structured Text (ST)

_HMI:_ CODESYS Visualisation

**Tools Needed to Simulate**

CODESYS V3.5 or later. No hardware required; fully simulation based.



















