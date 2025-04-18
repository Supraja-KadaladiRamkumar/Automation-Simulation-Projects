🌡 **Temperature Monitoring with Hysteresis**

This project implements a temperature threshold control system using Function Block Diagram (FBD) logic in CODESYS. The logic uses hysteresis to avoid frequent toggling near threshold values, an alarm to indicate excessive heat and includes a simple timer to simulate a gradual temperature rise.

🧩 **Logic Description**

The system monitors an analog temperature sensor and compares its value to high and low thresholds using hysteresis. 

🧮 **Key Functional Blocks**

- _**Sensor Reading:**_ Analog input from a temperature sensor is captured and moved into a variable.

- _**Hysteresis Logic:**_

  - Prevents output from toggling rapidly by applying a margin around threshold values.
  - High threshold logic: temp_reading ≥ (high_lim - hysteresis)
  - Low threshold logic: temp_reading ≤ (low_lim + hysteresis)

- _**TON Timer:**_ Used to enable calculation logic after a short delay (delay_timer), mimicking a smoother ramp-up of temperature in real-world scenarios.

✅ **Logical Flow**

1. The system waits for a signal (temp_sensor = TRUE) and a delay before enabling the main calculation logic (calc_enable).
2. The temperature value is read and stored in temp_reading.
3. Hysteresis comparisons determine whether high_lim_check or low_lim_check should be activated.
4. calc_enable is used in combination with hysteresis outputs to control the final logic path.

🔧 **Tools Used**

_**Platform:**_ CODESYS Simulation
_**Language:**_ Ladder Diagram (LD)

🛠️ **Tools Needed to Simulate**

- CODESYS Control Win Systray x64
- CODESYS Gateway Systray x64

📷 **Visual Reference**

Screenshots of the simulation are attached, including the visualization layout during the increase and decrease cycles.

📌 **Notes**

This is an intermediate-level project created during CODESYS practice to explore hysteresis implementation in temperature control systems and to understand how to structure robust threshold logic using FBD. 
