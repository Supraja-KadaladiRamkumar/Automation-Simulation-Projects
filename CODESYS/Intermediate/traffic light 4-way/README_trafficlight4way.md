🚦 **4-Way Traffic Signal Logic (PLC-Based)**

This project simulates a 4-way traffic signal system using Structured Text (ST) programming in CODESYS. It handles the traffic flow for north-south and east-west directions, including straight and left/right turns, along with a pedestrian crossing phase.

🧩 **Logic Description**

The logic mimics a real-world 4-way signal system with a stage-based flow using timers and control flags. It includes:

- Green, Yellow, and Red signal phases for all four directions
- Separate left and right turn handling
- Pedestrian walk signal phase integrated safely between vehicle cycles
- A finite state machine (FSM) approach to transition between stages

⏱️ **Signal Sequence (Simplified Flow)**

1. North-South straight green phase
2. North-South straight yellow
3. East-West straight green
4. East-West straight yellow
5. Pedestrian crossing (First)
6. North-South left/right turn green
7. North-South left/right turn yellow
8. East-West left/right turn green
9. East-West left/right turn yellow
10. Pedestrian crossing (Second)
11. Cycle resets to North-South straight green

Each stage transition is timer-driven to maintain realistic delays between changes.

🚶 **Pedestrian Logic**

- Pedestrian signals are active during safe vehicle red-light intervals
- Transitions through red → green → yellow → red
- Walk time: based on pedestrian_preset (10s), with yellow starting after pedestrian_preset_green (7s)

🔧 **Tools Used**

_**Platform:**_ CODESYS Simulation

_**Language:**_ Structured Text (ST)

🛠️ **Tools Needed to Simulate**
- CODESYS Control Win Systray x64
- CODESYS Gateway Systray x64
  
📷 **Visual Reference**

Screenshots of the HMI are attached, including the visualization layout before simulation and the simulation outputs for a few traffic light cycles.

📌 **Notes**

- This is an intermediate-level project created during CODESYS practice to explore a real life 4-way traffic signal scenario in ST.
- A separate code incorporating the stop block to resume/restart the program can be incorporated in future versions.
- Code is provided in 'traffic light 4 way.txt'.
