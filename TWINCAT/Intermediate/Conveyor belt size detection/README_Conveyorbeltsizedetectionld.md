🚧📦 **Object Sorting in Conveyor Belt – Ladder Logic**

This ladder logic program simulates a conveyor-based object sorting system that uses manual and sensor-based inputs to direct objects into either a small or big bin. It includes safety interlocks, fault detection, and manual overrides. It is functionally equivalent to the ST version, with some extra handling logic implemented in the final rung and comparison operations.

🧩 **Logic Description**

- The conveyor motor is activated when:
  - Start pushbutton is pressed (pb_start)
  - Process is reset
  - Output is latched
  - Safety interlocks (lock_safety1, lock_safety2) are not engaged
  - No object is detected (sensor_objects)
  - No faults are active
- A TON timer (motor_timer_conveyor) tracks how long the conveyor has been running:
  - If an object is detected within the first 5 seconds and a manual button (manual_input) is pressed, the object is considered small.
  - Otherwise, it's considered big and routed accordingly.
 - _Flags used:_
   - temp_object: Set when an object is detected during conveyor operation
   - temp_manual: Set when manual input is received within the correct time frame
   - set_inputs: Internally stores timing and manual selection logic for further rungs
 - _Bin assignment:_
    - If temp_object is true:
      - temp_manual = TRUE → Route to bin_small
      - Else → Route to bin_big
 - _Fault detection:_
    - If the manual input is not received within the timer duration, fault_button is set.
 - _Reset logic:_
    - Triggered by pb_reset or pb_stop, which clears:
      - Bins
      - Manual input and temp flags
      - Safety LED (lock_safety_led)
      - Any active faults
        
🔧 **Tools Used**

_**Platform:**_ Beckhoff TwinCAT 3.1

_**Language:**_ Ladder Diagram (LD)

🛠️ **Tools Needed to Simulate**

- TwinCAT XAE (Extended Automation Engineering) environment
- Weekly runtime license (valid for 7 days, can be renewed)

📷 **Visual Reference**

Screenshots of the output are attached, including before simulation and the simulation outputs for both bins and fault handling.

📌 **Notes**

- _Use of Permanent TRUE:_ The final rung uses a logical 1 (always TRUE) to guarantee execution every scan cycle. In ST, this would normally be handled in sequential code structure, but in LD, this visual placeholder ensures the rung is always evaluated.
- _Scan Order Awareness:_ Ladder logic executes top-to-bottom, left-to-right. The placement of the final "always-true" rung at the end ensures that cleanup logic like resetting timers and flags only occurs after all motor and fault conditions have been evaluated.
- This logic is ideal for demonstration or portfolio work showcasing real-world conveyor sorting use cases with time-based classification and manual override.
