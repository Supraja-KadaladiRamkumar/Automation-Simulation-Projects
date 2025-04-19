⚙️ **Motor Sequential Control – Ladder Logic**

This ladder logic program manages a sequential motor startup system with timing logic, fault detection, and manual reset capabilities. It is functionally equivalent to the ST version, with some extra handling logic implemented in the final rung and comparison operations.

🧩 **Logic Description**

The logic cycles three motors (motor1, motor2, motor3) one after another within a 35-second window, with built-in handling for motor faults, partial resets, and a full reset. The timing is preserved even during fault conditions using an offset mechanism.

⏱️ _**Timer and Motor Sequence**_

- The system sequentially starts three motors with a delay of 10 seconds between each (from 5s to 35s total):
  - T#0–5s → All motors off
  - T#5–15s → motor1 ON (⚙️ Low Limit Check)
  - T#15–25s → motor2 ON (⚙️ Medium Limit Check)
  - T#25–35s → motor3 ON (⚙️ High Limit Check)
  - T ≥ 35s → Triggers reset_limit_check, resets timer_offset := T#0S
- A TON timer is used to track elapsed time (motor_et), which drives the motor activation pattern and corresponding limit check stages.

🚨 _**Fault Handling**_

Each motor has its own fault input:
  - If fault_m1, fault_m2, or fault_m3 occurs, the current elapsed time is stored in timer_offset.
  - The affected motor is shut down, its LED turned OFF, and a global fault_led is turned ON.
  - Motors can be individually reset once the fault clears.

🔁 _**Reset Logic**_

- Global Reset (reset_all):
  - Stops all motors
  - Turns off LEDs
  - Clears all fault and reset flags
  - Resets the timer and timer_offset
    
- Individual Resets (reset_m1, reset_m2, reset_m3):
  - Clears only the fault and reset flags for all motors
  - Does not restart the motors unless conditions are met again

🧠 _**Permanent Rung Logic (Unique to LD & FBD)**_

- In LD and FBD only, the final rung contains always-true logic (1) connected to execute and handles advanced resets and fault management
- This ensures:
  - Timers and faults are synced correctly
  - The system doesn’t restart in a faulty or halfway state
  - Resets don't leave stale flags in memory

🔧 **Tools Used**

_**Platform:**_ Beckhoff TwinCAT 3.1

_**Language:**_ Ladder Diagram (LD)

🛠️ **Tools Needed to Simulate**

- TwinCAT XAE (Extended Automation Engineering) environment
- Weekly runtime license (valid for 7 days, can be renewed)

📷 **Visual Reference**

Screenshots of the output are attached, including before simulation and the simulation outputs for a motor and its fault handling.

📌 **Notes**

- _Use of Permanent TRUE:_ The final rung uses a logical 1 (always TRUE) to guarantee execution every scan cycle. In ST, this would normally be handled in sequential code structure, but in LD, this visual placeholder ensures the rung is always evaluated.
- _Scan Order Awareness:_ Ladder logic executes top-to-bottom, left-to-right. The placement of the final "always-true" rung at the end ensures that cleanup logic like resetting timers and flags only occurs after all motor and fault conditions have been evaluated.
