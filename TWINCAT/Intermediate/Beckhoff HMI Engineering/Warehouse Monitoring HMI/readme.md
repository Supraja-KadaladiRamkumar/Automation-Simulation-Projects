🏭 **Three-Zone Storage–Processing–Packaging Simulation**

This project demonstrates a multi-zone automated line with three main units:

- Zone 1 – Storage
- Zone 2 – Processing
- Zone 3 – Packaging
  
It combines the main Structured Text (ST) logic with a TwinCAT-engineered HMI for step-by-step visualisation of machine states and alarms.

🧩 **Process Flow**

_1. Start / Stop logic_

- Press Start to begin the cycle from Stage 0 (Idle).
- Stop immediately halts all activity and resets variables to a safe state.
  
_2. Zone 1 – Storage_
   
- Checks door and intrusion sensors and a configurable temperature range.
- If the temperature goes outside min/max limits or sensors are triggered, an alarm is raised.
  
_3. Zone 2 – Processing_

- Starts automatically when Zone 1 is ready.
- Includes machine malfunction detection and a human reset to clear faults.
- A 15 s timer represents the processing phase.
  
_4. Zone 3 – Packaging_

- Begins once Zone 2 signals ready.
- A packaging counter counts detected objects until the batch target is reached, then hands control back to Zone 1.

Timers between zones simulate transfer delays (10 s each).

🧰 **Control Logic**

- Core program written in Structured Text.
- CASE-like stage sequencing:
  - Stage 0: Idle
  - Stage 1: Storage
  - Stage 2: Processing
  - Stage 3: Packaging
- Each zone has: Running, Ready, and Alarm booleans.
- Interlocks that prevent the next stage from starting if alarms or faults are active.
  
💻 **HMI Design**

- Built in TwinCAT HMI Engineering.
- Manual toggle switches simulate real sensors:
  - Door open
  - Human intrusion
  - Machine malfunction
  - Object detection
- Temperature input is entered manually for the simulation.

_HMI LED Colour Code_

- Green – LED on (condition true)
- Red – LED off
- Yellow – Alarm active
- Grey – Signal not applicable for that zone

🔧 **Tools Used**

_**Platform:**_ Beckhoff TwinCAT 3.1 XAE 

_**Language:**_ Structured Text (ST)

_**HMI:**_ TwinCAT HMI Engineering 

🛠️ **Tools Needed to Simulate** 

- TwinCAT XAE (Extended Automation Engineering) environment
- TwinCAT HMI Engineering
- Weekly runtime license (7-day free license, renewable)


📌 **Notes**

- The HMI is designed for training and demonstration, not for production control.
- All LEDs, alarms and timers reset cleanly when the Stop button is activated, ensuring safe shutdown at any stage.
- In an industrial setup, the toggled inputs would be actual field sensors (proximity, intrusion, temperature, etc.). Here they are manually set for demonstration.
