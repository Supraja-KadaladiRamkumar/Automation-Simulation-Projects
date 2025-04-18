🕕 **Temperature Monitoring and Alarm Handling with Timers**

This program simulates a temperature monitoring system with alarm handling using timers in CODESYS' Functional Block Diagram (FBD) environment. The core idea is to trigger different types of alarms based on temperature conditions.

🧩 **Logic Description**

1. A simulated temperature increases over time via a timer.
2. Heater is turned ON when simulation begins.
3. Alarm types are triggered based on the current temperature value:
   - **Info**: Temp is safe and within normal bounds.
   - **Warning**: Temp is near the SP (Set Point).
   - **Error**: Temp crosses the maximum threshold.
4. A reset button allows the user to clear the alarms.
5. All alarms are logged and visualized with timestamps on the HMI.

💻 **Visualization Overview**

The HMI interface includes:

- _**Operator Reset**_ button to acknowledge/clear alarms.
- _**Temp Sensor**_ button to enter temperature values.
- _**Heater ON (Green Lamp)**_ to indicate system is active.
- _**Overtemperature Lamp (Red)**_ to signal an error condition.
- _**Alarm Table**_ to display timestamped alarm messages in a structured format.

🔧 **Tools Used**

_**Platform:**_ CODESYS Simulation

**_Language:_** Function Block Diagram (FBD)

🛠️ **Tools Needed to Simulate**

- CODESYS Control Win Systray x64
- CODESYS Gateway Systray x64
  
📷 **Visual Reference**

Screenshots of the HMI are attached, including the visualization layout before simulation and for the various temperature ranges during simulation.

📌 **Notes**

- Alarm types (Info, Warning, Error) are configured in the Alarm Configuration tab.
- This is an intermediate-level project created during CODESYS practice to implement alarms in temperature control systems
- Future enhancements include adding trends/graphs to show temperature history.


