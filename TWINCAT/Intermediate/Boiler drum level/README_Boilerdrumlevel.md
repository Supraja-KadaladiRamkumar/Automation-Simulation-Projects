🧪 **Tank Liquid Level Simulation**

This PLC program simulates a tank-level filling and draining system. The system maintains the level between 25% and 75% using two sequential operations: filling through an inlet valve and draining through an outlet valve. The simulation mimics level increase and decrease through arithmetic operations on a level variable, while LED indicators and a progress bar represent system status on the HMI.

🧩 **Logic Description**

This project simulates a 2-phase process in a tank and includes input and drain phases, each with its own timers, valves, and screen indicators.

_**Rung 1:**_

  - Uses an SR (Set-Reset) block.
  - Set conditions: NC Stop PB, NC M2, NO Start PB.
  - Reset condition: GE comparator checks if level reading ≥ 75% of max value.
  - Output: M1 memory bit is set.

_**Rung 2:**_
  - M1 turns on the input valve and input LED.

_**Rung 3:**_

  - M1 and input valve enable a timer.
  - Timer is reset by its NC Done bit.
  - Done bit triggers the Input_Calc_Enable bit.

_**Rung 4:**_

When Input_Calc_Enable and M1 are on:
  - Level reading increases by 1.
  - Temporary value is stored in offset and moved back to level reading.

_**Rung 5:**_

  - GE comparator (level ≥ 75%) triggers Set input of SR to turn on M2.
  - Reset conditions: NC M1 and GE comparator (level ≤ 25%).

_**Rung 6:**_

M2, NC M1, and NC Stop PB turn on drain valve and drain LED.

_**Rung 7:**_
  
  - M2 and drain valve start another timer.
  - Timer done bit triggers Drain_Calc_Enable and restarts timer (NC Done).

_**Rung 8:**_

When Drain_Calc_Enable and M2 are on:
  - Level reading decreases by 1.
  - Temporary value is stored in offset and moved back to level reading.

This forms a cyclic process that fills and drains the tank between two level limits.

🖥️ **HMI Overview**

- Two pushbuttons: Start and Stop.
- Two LEDs indicate input and drain valve status.
- A progress bar represents the tank level.
- Two hourglass images symbolically show inflow and outflow.
  
⚠️ Note: The HMI is basic due to TwinCAT's limited visualization capabilities. It is intended for simulation and understanding of the process rather than high-end interaction.

🔧 **Tools Used**

_**Platform:**_ Beckhoff TwinCAT 3.1

_**Language:**_ Ladder Logic (LD)

🛠️ **Tools Needed to Simulate**

- TwinCAT XAE (Extended Automation Engineering) environment
- Weekly runtime license (valid for 7 days, can be renewed)
  
📷 **Visual Reference**

Screenshots of the output are attached, including before simulation and the simulation outputs for both phases of the process.

📌 **Notes**

- A future enhancement could simulate liquid flow visually instead of using a static progress bar, making the tank level animation more realistic.
- While TwinCAT provides basic HMI features, this project demonstrates screen switching and real-time updates using available elements.
- The logic ensures the tank doesn’t overflow (≥75%) or empty completely (≤25%).
- Additions and subtractions mimic liquid movement.
