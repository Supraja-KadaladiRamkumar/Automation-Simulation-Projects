🌡️ **Temperature Controlled Heating with Hysteresis  (ST)**

This Structured Text (ST) program models a one-way hysteresis temperature control system, where temperature is gradually increased and monitored against a set maximum limit.

🧩 **Logic Description**

The system monitors an analog temperature sensor and compares its value to high thresholds using hysteresis. However, unlike the other version (Temperature Monitoring with Hysteresis/ Overheat Alarm with Hysteresis), there is no simulated cooling phase—the alarm is not reset by dropping temperature, but only through a manual reset condition (reset).

🧮 **Key Behaviors**

- Gradual temperature increase using a timer gate within a WHILE loop.
- Heater is turned off once temp exceeds set_point + hysteresis.
- Alarm is triggered at max_limit, disabling further operation.
- Manual reset resets alarm and emergency stop flags.

🔧 **Tools Used**

**_Platform:_** CODESYS Simulation

_**Language:**_ Structured Text (ST)

🛠️ **Tools Needed to Simulate**

- CODESYS Control Win SysTray (x64)
- CODESYS Gateway SysTray (x64)
  
📌 **Notes**

- This is an intermediate-level project created during CODESYS practice to explore state-driven heating logic with one-way hysteresis and latching behavior.
- No reverse/cooling loop is implemented here—this model focuses on rising temperature and emergency cutoff only.
- The logic is optimized for clarity and simulation; actual implementations may vary based on sensor response time and hardware configuration.
- Code is provided in 'temp control heating system ST.txt'.
- No output is shown, as this is a syntax and logic practice file.
- Can be adapted for use in temperature threshold safety systems, heating-only process control, or alarm-based supervisory logic.
