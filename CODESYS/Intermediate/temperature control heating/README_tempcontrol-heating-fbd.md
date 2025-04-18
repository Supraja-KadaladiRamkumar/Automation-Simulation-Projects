🌡 **Temperature Controlled Heating with Hysteresis (FBD)**

This program simulates a one-way hysteresis temperature monitoring system using Function Block Diagram (FBD) in CODESYS. The temperature increases gradually, and an alarm (buzzer) is triggered when the reading exceeds a set high threshold (max_limits) plus hysteresis. 

🧩 **Logic Description**

The system monitors an analog temperature sensor and compares its value to high thresholds using hysteresis. However, unlike the other version (Temperature Monitoring with Hysteresis/ Overheat Alarm with Hysteresis), there is no simulated cooling phase—the alarm is not reset by dropping temperature, but only through a manual reset condition (reset).

🧮 **Key Functional Blocks**

- Gradual temperature simulation using a timer and conditional enable logic.
- Hysteresis logic prevents premature triggering of the alarm due to signal fluctuations near the setpoint.
- SR flip-flop (set-reset block) latches the alarm state until a separate reset condition (reset AND temp_reading < max_limits) is met.
- TON Timer: Used to enable calculation logic after a short delay (delay_timer), mimicking a smoother ramp-up of temperature in real-world scenarios.

🔧 **Tools Used**

_**Platform:**_ CODESYS Simulation

_**Language:**_ Function Block Diagram (FBD)

🛠️ **Tools Needed to Simulate**

- CODESYS Control Win Systray x64
- CODESYS Gateway Systray x64

📌 **Notes**

- This is an intermediate-level project created during CODESYS practice to explore hysteresis implementation in temperature control systems using RS flip-flop.
- The logic is well-suited for systems like thermal limiters or overheat alarms where only high-threshold monitoring is needed.
