🌡️ **Temperature Control Simulation**

This project simulates a simple heating–cooling cycle with an alarm mechanism. It combines classic PLC logic with an engineered TwinCAT HMI for live process monitoring.

🧩 **Logic Description**

_Heating phase_

- Temperature rises by 2 °C per second until the upper limit is reached.
- Once the limit is exceeded, an Alarm is triggered.
  
_Cooling phase_

- After the alarm, the system activates the Cooler.
- Temperature decreases by 2 °C per second until the lower limit is reached.
- Alarm resets automatically.
  
_Idle / Reset_

- Stop to force reset all variables and return to idle state incase of emergencies.

🧰 **Control Logic**

- Main logic handles temperature changes, alarm logic and timers.
- _Main variables:_
  - temp_timer – controls the heating interval
  - temp_cooling_timer – controls the cooling interval
  -  cooler_timer – manages cooler operation time
- The logic ensures smooth switching between heating, cooling and idle phases.

💻 **HMI Logic**

  - _Common Controls:_ Start/Stop buttons and live temperature sensor indicator.
  - _Dynamic Feedback:_
    - Heating phase shows current °C and remaining heating time.
    - Cooling phase displays remaining cooling time.
    - Alarm color changes (⚠️ yellow) when upper limit is reached.
  - _Visual Components:_
    - Distinct indicators for Sensor, Alarm and Cooler.

🔧 **Tools Used**

**_Platform:_** Beckhoff TwinCAT 3.1

_**Language:**_ Structured Text (ST)

🛠️ **Tools Needed to Simulate**

- TwinCAT XAE (Extended Automation Engineering) environment
- TwinCAT HMI Engineering
- Weekly runtime license (valid for 7 days, can be renewed)


⚠️ Note: The HMI is basic due to TwinCAT's limited visualization capabilities. It is intended for simulation and understanding of the process rather than high-end interaction.

📌 Notes

- ST code ensures dynamic behavior and calculations.
- While TwinCAT provides basic HMI features, this project demonstrates real-time updates using available elements.
🔧 Tools Used
