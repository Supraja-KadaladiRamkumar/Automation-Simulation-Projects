📦 **Conveyor Object Sorting – HMI Based**

This project implements a conveyor-based object sorting system in Structured Text (ST) using TwinCAT 3. It classifies objects as small or big using a sensor and size input logic, routes them using diverters, and maintains count-based histograms to track object flow into bins. It includes conveyor logic, overflow detection, reset routines, and HMI display elements including trend indicators.

🧩 **Logic Description**

Objects are identified and sorted into size using sensors. A histogram on the GUI shows real-time counts of sorted objects to help monitor trends and detect anomalies like overflow conditions.

_**1. Conveyor Belt Control**_

  - Conveyor starts when:
    - start is pressed
    - Either initial start or m1 already TRUE
    - stop and reset_whole are NOT active
- Object detection pauses the conveyor after a 5-second delay using start_timer.
- Conveyor resumes only if no object is detected.

_**2. Object Detection & Diverter Logic**_

- Rising edge (r_trig_obj) triggers sorting.
- Diverters are set based on object_size = 0 (small) or 1 (big), and only activate if the conveyor has stopped.
- RS Flip-Flops (RS_diverter_small, RS_diverter_big) latch diverters until object clears or reset is triggered.

_**3. Small Bin Logic and Big Bin Logic**_

- 2-second pulse simulates sorting delay into bin.Counter (small_count) tracks items (max 5 per pack).
- Histogram array histogram_small[0..4] visualizes cumulative item count.
- On 5 items: move_to_pack_small becomes TRUE.
- Overflow (>5) triggers overflow_limit_small.
- Big Bin Logic has the same structure using big_count, histogram_big, and overflow_limit_big.

_**4. Overflow Detection and Blinking Alerts**_

- If item count > 5, overflow flags (overflow_limit_small/big) activate.
- LEDs blink via 500ms timers (blink_timer_small, blink_timer_big) to indicate overflow status.

_**5. Reset & Emergency Stop**_

- Resets all flags, diverters, counts, timers, and histogram arrays.
- Acts as a global fallback or emergency routine.

📈 **Trend Observation**

_**Real-Time Sorting Overview:**_

- _Box Count – Small_ 📦
  
Displays the accumulation of small boxes. A rising bar indicates successful sorting by the small diverter. When this bar approaches the 20-box mark, it’s a cue to monitor for overflow or pack-out delays.

- _Box Count – Big_ 📦📦
  
Reflects the count of large boxes sorted via the big diverter. A sudden imbalance between the two histograms may hint at detection inconsistencies or mechanical issues with diverters.

- _Overflow Indicators_ 🚨
  
Red lamps below each histogram highlight when bin capacity is exceeded. These act as immediate flags for operational intervention—reminding the operator to pause sorting and clear excess stock before proceeding.

This allows quick diagnosis of:
- Uneven box distribution across diverters.
- Delays in packing that might cause system backup.
- Overflow risks that could halt automated processing.

🖥️ **HMI Overview**

- Start, Stop, and Reset buttons
- Radio buttons for simulating object size
- Push button for object detection sensor simulation
- Indicators for:
  - Conveyor status
  - Diverters (small & big)
  - Packing LEDs
  - Overflow alerts (blinking) and mesaages
- Histogram display for:
  - histogram_small[0..4]
  - histogram_big[0..4]
- Toggle buttons between screens for real-time monitoring
  
⚠️ Note: The HMI is basic due to TwinCAT's limited visualization capabilities. It is intended for simulation and understanding of the process rather than high-end interaction.

🔧 **Tools Used**

_**Platform:**_ Beckhoff TwinCAT 3.1

_**Language:**_ Structured Text (ST)

🛠️ **Tools Needed to Simulate**

- TwinCAT XAE (Extended Automation Engineering) environment
- Weekly runtime license (valid for 7 days, can be renewed)
  
📌 **Notes**

- Code is provided in 'conveyor belt sorting histogram st.txt'.
- Overflow alert helps in limiting operations when critical limits are reached.
- This project simulates a real-world sorting system with visual tracking, automated diverter control, and overflow safeguards. 
