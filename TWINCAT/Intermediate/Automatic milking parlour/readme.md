🐄 **Automated Milking Parlour Simulation**

This project demonstrates an automated milking parlour process using Structured Text (ST) with a TwinCAT HMI for process visualisation, alarms and event logging.

The simulation covers the complete process from cow entry through milking, cow exit and cleaning.

🧩 **Process Flow**

_**1. Idle / Start**_

Press Start to begin the cycle. The system starts from Stage 0 and moves into the animal detection phase.

_**2. Animal Detection**_

The cow entry and presence sensors are used to control the entry gate. A timeout alarm is generated if the cow does not enter within the configured time.

_**3. Milking Preparation**_

The vacuum pump builds up to the required pressure before the milking unit is extended and the system moves to active milking.

_**4. Milking**_

Milk extraction is simulated using a decreasing flow rate. Milk collected from each cow is stored in an array and displayed in the HMI table.

_**5. Animal Exit**_

The exit gate opens after milking. An exit timeout alarm is generated if the cow does not leave within the configured time.

_**6. Cleaning**_

Quick cleaning is performed between cows. Once the day's milking is complete, the system performs a full cleaning cycle before returning to Idle.

🔄 **Stage Sequence**

Stage 0: Idle
Stage 1: Animal Detection
Stage 2: Milking Preparation
Stage 3: Milking Active
Stage 4: Milking Complete
Stage 5: Animal Exit
Stage 6: Quick Cleaning
Stage 7: End of Day Full Cleaning

🚨 **Alarms & Events**

The TwinCAT HMI includes logged events for different process conditions, including:

- Critical alarms
- Serious alarms for cow entry, cow exit, vacuum and milking
- Less serious cleaning alarms
- End of cycle information
- End of day information

🖥️ **HMI Overview**

- Built in TwinCAT HMI Engineering, the HMI provides live visualisation of the milking process, including stage information, equipment states, timers, counters, milk collection and active alarms.
- The HMI also provides manual controls for simulating field inputs and reset conditions during the process.
- The Logged Events view uses the TwinCAT HMI Typesystem and Event Classes to display process events according to their severity, including critical, serious and less serious alarms, along with cycle and end of day information.
- Milk collected from each cow is displayed directly in the HMI using a table, allowing individual cow production to be monitored during the simulation.
  
🔧 **Tools Used**

  _**Platform:**_ Beckhoff TwinCAT 3.1

  _**Language:**_ Structured Text (ST)

🛠️ **Tools Needed to Simulate**

- TwinCAT XAE (Extended Automation Engineering) environment
- Weekly runtime license (valid for 7 days, can be renewed)
  
📌 **Notes**

- Code is provided in 'Automatic milking parlour st.txt'.
- All process inputs are manually simulated through the HMI. In a real installation, these inputs would come from physical sensors and field devices.
- The simulation includes separate controls for process reset, emergency stop, abort and stage specific alarm resets.
- Future Improvements could include flow rate alarms during the active milking stage.


