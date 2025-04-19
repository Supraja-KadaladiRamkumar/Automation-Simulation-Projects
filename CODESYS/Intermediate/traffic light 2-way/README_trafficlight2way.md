🚦 **2-Way Traffic Light Control System (North-South / East-West)**

This program simulates a 2-way traffic control system with timed light transitions for North-South and East-West directions using structured text and visualization in CODESYS.

🧩 **Logic Description**

_**Key Behaviors:**_

- The system starts with North-South (NS) Green, and East-West (EW) Red.
- After 15 seconds, NS Green switches to NS Yellow.
- After 5 seconds, NS Yellow switches to NS Red, and EW Green is activated.
- After 15 seconds, EW Green turns into EW Yellow.
- After 5 seconds, EW Yellow ends, and NS Red is cleared — resetting the cycle.
- The cycle continues as long as start is active and stop is not pressed.

_**Timer Logic:**_

- A TON timer (traffic_timer) controls phase timing.
- elapsed_time := traffic_timer.ET tracks time progression in the current phase.
- The timer resets after every transition to manage the next timed phase correctly.

**🖥 Visualization**

The simulation includes a user-friendly visual layout featuring:
- LED indicators for each light: red, yellow, and green for both NS and EW directions.
- Start/Stop push buttons to control the signal loop.
- A simple compass layout to denote direction.
- Lights change dynamically based on logic, allowing easy real-time observation.

🔧 **Tools Used**

_**Platform:**_ CODESYS Simulation

_**Language:**_ Structured Text (ST)

🛠️ **Tools Needed to Simulate**
- CODESYS Control Win Systray x64
- CODESYS Gateway Systray x64

📷 **Visual Reference**

Screenshots of the HMI are attached, including the visualization layout before simulation and the simulation outputs for both East-West and North-South traffic light cycles.

📌 **Notes**

- This is an intermediate-level project created during CODESYS practice to explore a simple and straightforward 2-way traffic signal scenario in ST.
- Code is provided in 'traffic light 2 way.txt'.
- Future improvisations include adding a pedestrian crossing with dedicated pedestrian halt zones for more accurate signaling.
