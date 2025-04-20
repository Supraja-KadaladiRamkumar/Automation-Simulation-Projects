🚦 **Traffic Light Control – Ladder Diagram (LD)**

This Ladder Diagram (LD) implementation simulates a three-stage traffic light (Green → Yellow → Red) controlled by elapsed time using a TON timer. The logic mirrors the FBD version, but is visually represented through relay-like rungs for clarity and hardware familiarity.

🧩 **Logic Description**

- A TON timer (traf_timer) is activated when:
  - start_pb is ON
  - stop_pb is OFF
  - traf_timer.q is FALSE
- The timer runs for 20 seconds.
- The elapsed time (traf_timer.ET) controls the light state transitions based on comparison blocks.

🟢🟡🔴 **Light Transition Logic**

- Green: On at start and remains until 7s.
- Yellow: From 7s to 10s.
- Red: From 10s to 20s.

⚙️ **Timer Reset & Cycling**

- After 20s, the timer completes its run and resets due to the logic in the first rung.
- This ensures the traffic light cycles continuously until stop_pb is pressed.

🔧 **Tools Used**

_**Platform:**_ Beckhoff TwinCAT 3.1

_**Language:**_ Ladder Diagram (LD)

🛠️ **Tools Needed to Simulate**

- TwinCAT XAE (Extended Automation Engineering) environment
- Weekly runtime license (valid for 7 days, can be renewed)

📷 **Visual Reference**

Screenshots of the output are attached, including before simulation and during simulation.

📌 **Notes**

- The logic uses comparators (GT, LT, LE) to define exact timing windows.
- Uses normally closed and normally open contacts to ensure safe switching.
- A clean visual representation suited for relay logic users or control engineers comfortable with physical circuit diagrams.
