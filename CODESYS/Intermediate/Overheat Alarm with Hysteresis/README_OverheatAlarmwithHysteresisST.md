🌡️ **Temperature Monitoring with Hysteresis (ST)**

This Structured Text (ST) program implements hysteresis logic for temperature control. When the simulated temperature exceeds the high threshold plus hysteresis, an alarm is triggered. Once the temperature falls below the low threshold minus hysteresis, the alarm is reset. This avoids frequent toggling around threshold values and simulates realistic behavior for temperature-based systems.

🧩 **Logic Description**

_**Hysteresis Control:**_ Introduces buffer zones around threshold limits to prevent frequent toggling of the alarm signal.

**_Timers:_** Two TON delay timers are used to simulate temperature changes over time and provide smoother transitions in both heating and cooling phases.

_**Loop-based Simulation:**_ WHILE loops are used to increment and decrement temperature readings during simulated heat-up and cool-down phases.

🔧 **Tools Used**

**_Platform:_** CODESYS Simulation

_**Language:**_ Structured Text (ST)

🛠️ **Tools Needed to Simulate**

- CODESYS Control Win SysTray (x64)
- CODESYS Gateway SysTray (x64)
  
📌 **Notes**

- This is an intermediate-level project created during CODESYS practice to explore loop-based simulation and hysteresis behavior in ST.
- The logic is optimized for clarity and simulation; actual implementations may vary based on sensor response time and hardware configuration.
- Code is provided in 'Overheat Alarm with Hysteresis ST.txt'.
- No output is shown, as this is a syntax and logic practice file.
