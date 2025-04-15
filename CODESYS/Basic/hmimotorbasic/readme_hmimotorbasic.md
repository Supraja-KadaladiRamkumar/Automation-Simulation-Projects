🌀 Motor Speed Control with Timer & Limit Logic (LD)

This project demonstrates a simple motor speed control system implemented in Ladder Logic Diagram (LD) with Function Blocks using timers, comparators, and arithmetic blocks. The motor starts when the input is toggled and accelerates in steps until a user-defined limit is reached. An HMI interface allows user interaction.

🧩 **Logic Description**

_**Rung 1:**_ Input button sets the motor (Set coil).
_**Rung 2:**_ Stop button resets the motor (Reset coil).
_**Rung 3:**_ Motor ON & NC of Timer's Done bit triggers a TON timer (preset to 20s).
_**Rung 4:**_ If motor is running, Timer is done, and Break is OFF → an ADD block increments motor speed by 40.
_**Rung 5:**_ GE block compares current motor speed with user-defined dial value. When maximum value set is reached, Break is triggered. This way the motor runs at a constant speed from this point.

🔧 **Tools Used**
- _**Platform:**_ CODESYS Simulation
- _**Language:**_ Ladder Diagram (LD)

🛠️ **Tools Needed to Simulate**
- CODESYS Control Win Systray x64
- CODESYS Gateway Systray x64

📷 Visual Reference
- Screenshots of Simulation (PLC + HMI) are attached.

📌 **Notes**
HMI includes:
- Toggle buttons for Input and Stop
- LED indicating Motor Running
- Dial for Setting Speed Limit
- Scale to display Motor Speed Increment

  No manual output display; logic visualized through simulation.
