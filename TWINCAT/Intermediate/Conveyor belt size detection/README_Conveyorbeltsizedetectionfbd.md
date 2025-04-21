🚧📦 **Object Sorting – Function Block Diagram**

This program automates a conveyor belt sorting system using Function Block Diagram (FBD) logic. The system classifies objects based on size using a sensor + manual input method and sorts them into big or small bins. It also integrates safety conditions, fault detection, and a reset routine.

🧩 **Logic Description**

_**Conveyor Control**_
- The conveyor motor (conveyor_motor) is activated when:
    - Start button (start_pb) is pressed
    - Conveyor is already running
    - Safety zone is clear (safety_zone1, safety_zone2)
    - No fault or reset is active
    - No object is currently detected (object_detected_sensor is FALSE)
  - Timer block (timer_conveyor) ensures that object detection occurs within a 10-second time frame.

_**Object Detection & Sorting**_
- If an object is detected before the timer completes, it's tagged as object_detected_sensor.
- If manual input (input_manual) is provided during the first 5 seconds:
  - The object is routed to the small bin (small_bin)
- Otherwise, it is routed to the big bin (big_bin)

_**Fault Detection**_

- If the object is not sorted within the timer window without manual input, a fault is triggered (fault).
- Fault is also set via FBD logic using AND/OR combinations and is reset by reset_pb.

_**Reset Logic**_
- On pressing reset_pb, a structured text (ST) block resets:
  - Safety zone indicators
  - Manual and object detection flags
  - Fault flags

_**Safety Zone LED**_
- The safety_zone_led is activated when the reset condition is met, indicating the system is safe and ready.

🔧 **Tools Used**

_**Platform:**_ Beckhoff TwinCAT 3.1

_**Language:**_ Functional Block Diagram (FBD)

🛠️ **Tools Needed to Simulate**

- TwinCAT XAE (Extended Automation Engineering) environment
- Weekly runtime license (valid for 7 days, can be renewed)

📌 **Notes**
- _Efficient Block Usage:_ By reusing inputs and chaining logical blocks, FBD offers a clean and intuitive flow while maintaining the flexibility of ST.
- _Hybrid Inspiration:_ This FBD logic draws from both ST and LD approaches — it adopts ST’s compact logic expression style and LD’s structured rung evaluation with an always-true execution network.
- This version is ideal for showcasing clean industrial FBD modeling of a typical sensor-based sorting conveyor system.
