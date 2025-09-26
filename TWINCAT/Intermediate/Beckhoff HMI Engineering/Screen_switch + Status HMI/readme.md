🏭 **Multi-Phase Packaging Line Simulation**

This project simulates a four-step packaging process - Idle, Filling, Processing and Packaging. It combines simple PLC logic with a TwinCAT-engineered HMI for clear, screen-by-screen visualization of each phase.

🧩 **Logic Description**

_Process flow_

1. Idle: System waits in standby until Start is pressed.

2. Filling: Filling LEDs turn green while material is dispensed.

3. Processing: Product is processed; only the processing LED is active.

4. Packaging: Final packaging stage with its LED indicator.

_Emergency stop_

Stop immediately halts the process and resets all indicators, regardless of the current phase.

🧰 **Control Logic**

- Main logic handles case switch with a single 15-second phase timer.
- A CASE statement steps through each stage and toggles LEDs:
  - idle_led
  - filling_led
  - processing_led
  - packaging_led
- Variables reset to a safe state whenever Stop is pressed.

💻 **HMI Logic**
- _Common Controls:_ Start/Stop buttons and navigation between screens.
- _Screen-specific LEDs:_ Only the LED of the current phase is visible and changes red ➜ green as the phase completes.
- Each screen shows just its own active phase indicator for quick, uncluttered status checking.

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
- All LEDs and timers reset cleanly when the Stop button is activated, ensuring safe shutdown at any stage.
- The project shows how a simple ST program can drive a multi-screen HMI with phase-specific visibility and real-time feedback.

