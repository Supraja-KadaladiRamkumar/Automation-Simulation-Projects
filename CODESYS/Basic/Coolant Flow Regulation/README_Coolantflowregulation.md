🌡️ **Pump Speed Control Based on Temperature Deviation (ST)**

This project simulates pump speed control using a temperature sensor input. Implemented in Structured Text (ST), the logic dynamically adjusts the pump speed based on the deviation from a setpoint. It also includes a delay timer and an alarm condition once a maximum threshold is reached.

🧩 **Logic Description**

- **Inputs:**
  - start: Starts the process
  - stop: Stops the process
  - alarm: Engages when a maximum threshold is crossed
  - SP: Temperature setpoint
  - delay_time: Preset time to wait before reading temperature

- **Working:**
  
  - The process starts when start is ON, and both stop and alarm are OFF.
  - A delay timer ensures that temperature readings are taken after a set period.
  - If the timer finishes:
      - The temperature is incremented (temp_reading), and deviation is calculated
      - Based on the deviation from the setpoint, the pump speed is adjusted:
        - Minor deviations: slower ramp-up
        - Moderate deviations: scaled increase
        - Large deviations: fast increase, capped at 100%
  - Once the temp_reading exceeds max_limit, the pump is forced to maximum speed and an alarm is triggered.

🔧 **Tools Used**

- _**Platform:**_ CODESYS Simulation
- _**Language:**_ Structured Text (ST)

🛠️ **Tools Needed to Simulate**

- CODESYS Control Win Systray x64
- CODESYS Gateway Systray x64

📌 **Notes**

- Code is provided in 'coolant flow regulation.txt'
- Ideal for understanding real-time parameter control, timer operations, and conditional logic in Structured Text.
- No output is shown, as this is a syntax and logic practice file
