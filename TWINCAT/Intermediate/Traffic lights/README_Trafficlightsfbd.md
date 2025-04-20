🚦 **Traffic Light Control – Function Block Diagram (FBD)**

This FBD version of the traffic light controller uses a TON timer to manage the transitions between green, yellow, and red lights over a 20-second cycle. The design is modular and uses comparison and logical AND blocks to control light activation based on elapsed time.

🧩 **Logic Description**

- The system starts when:
  - start input is ON
  - stop input is OFF
  - traffic_timer.q is FALSE
- A TON timer (traffic_timer) runs for 20 seconds (t#20s).
- The current value of traffic_timer.ET (elapsed time) controls the lighting stages via logic blocks.

🟢🟡🔴 **Light Transition Logic**

- Green → Yellow (after 7s)
- Yellow → Red (after 10s)
- Red → Green (after 20s and timer resets)

⏱️ **Timer Logic**

- The timer is triggered when:
  - start = TRUE
  - stop = FALSE
- On completion (ET = 20s), the logic will cycle again due to how green light activation is conditioned on the timer being inactive.

🔧 **Tools Used**

_**Platform:**_ Beckhoff TwinCAT 3.1

_**Language:**_ Functional Block Diagram (FBD)

🛠️ **Tools Needed to Simulate**

- TwinCAT XAE (Extended Automation Engineering) environment
- Weekly runtime license (valid for 7 days, can be renewed)
  
📌 **Notes**

- Each stage uses logical AND blocks to ensure precise activation conditions.
- Time comparisons (<, >, <=) are used to tightly control transitions.
- Logical dependencies between light states help prevent overlapping outputs.
