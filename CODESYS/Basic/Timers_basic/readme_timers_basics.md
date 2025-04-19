⏱️ **Timers – Basic (CODESYS)**

This project demonstrates the basic usage of timers in **Ladder Logic** using **CODESYS**. It covers **ON delay**, **OFF delay**, and **pulse** timers with simple input/output control.

🧩 **Logic Description**

### 1. TON (ON Delay Timer)
- **Trigger:** `motor` is activated when `inp` is high
- **Timer:** 5-second delay using `TON_0`
- **Output:** `led` turns ON after the timer completes

### 2. TOF (OFF Delay Timer)
- **Trigger:** `switch`
- **Timer:** 10-second OFF delay using `off_delay`
- **Output:** `led_off` remains ON for 10 seconds after `switch` goes LOW

### 3. TP (Pulse Timer)
- **Trigger:** `pulse_inp`
- **Timer:** 10-second pulse using `pulse`
- **Output:** `pulse_op` turns ON for exactly 10 seconds once triggered

🔧 **Tools Used**
- **Platform:** CODESYS Simulation
- **Language:** Ladder Diagram (LD)

🛠️ **Tools Needed to Simulate**
- CODESYS Control Win Systray x64
- CODESYS Gateway Systray x64

📌 **Notes**
- Timers are configured using **preset time values** like `T#5S` (5 seconds).
- The `Q` output is used to drive the respective outputs.
- This project is for **practice and understanding core timer functionalities** in Ladder Diagrams.
