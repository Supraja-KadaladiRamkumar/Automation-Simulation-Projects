🚦 **3-Way Traffic Signal Logic (PLC-Based)**

This project implements a 3-way traffic signal control system using Structured Text programming in a PLC environment. The system coordinates traffic from North-South, West-South, and North-West directions, integrating pedestrian crossing functionality as well.

🧩 **Logic Description**

_**Traffic Lights Covered:**_

- North-South Straight
- South-North Straight
- West-South Right Turn
- North-West Right Turn
- West-North Free Left Turn
- South-West Free Left Turn
- Pedestrian Crossing

_**Timers Used:**_

- traffic_timer: Controls the duration for each traffic phase (timer_preset: 20 seconds).
- pedestrian_timer: Manages the pedestrian crossing time (pedestrian_preset: 10 seconds).
- The timer resets after every transition to manage the next timed phase correctly.

_**Main Signals:**_
  
- Green, yellow, and red lights for each direction.
- Pedestrian crossing signal controlled based on traffic states.

🚦 **Traffic Signal Logic Phases**

1. _Phase 1 – NS/SN Straight Green_
   
   Both NS and SN directions are given green if no pedestrian request or conflicting traffic.

2. _Phase 2 – NW Right Green_
   
   After NS/SN yellow phase, NW gets a green for right turn.

3. _Phase 3 – Pedestrian Crossing_
   
   After NW right turn, all signals turn red and pedestrian crossing is enabled for the preset time.

4. _Phase 4 – WS Right Green_
   
   Once pedestrian phase ends, WS gets a right turn green.

5. _Reset Phase – Back to NS/SN Straight Green_
   
   After WS yellow, the cycle resets to NS and SN straight green.

6. Except during the pedestrian cross time period, the green light of 2 left turns remain on throughout.

🔧 **Tools Used**

_**Platform:**_ CODESYS Simulation

_**Language:**_ Structured Text(ST)

🛠️ **Tools Needed to Simulate**

- CODESYS Control Win Systray x64
- CODESYS Gateway Systray x64
  
📷 **Visual Reference**

Screenshots of the HMI are attached, including the visualization layout before simulation and the simulation outputs for a few traffic light cycles.

📌 **Notes**

- A single pedestrian crossing LED is included in this 3-way logic. It activates during the pedestrian phase and applies to all directions at once.
- In the planned 4-way version, pedestrian functionality will be enhanced with two dedicated pedestrian halt zones for more accurate signaling.
- The pedestrian crossing is included in the logic and shown in the HMI, but not with individual signal controls or button inputs per crosswalk.
- A separate code incorporating the stop block to resume/restart the program can be incorporated in future versions. 
- Code is provided in 'traffic light 3 way.txt'.
