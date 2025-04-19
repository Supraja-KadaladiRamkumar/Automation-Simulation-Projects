⚙️ **Motor Control – Structured Text**

This program simulates a multi-stage motor sequence where three motors run one after another based on a timer cycle using Structured Text (ST) in TwinCAT.

🧩 **Logic Description**

The logic cycles three motors (motor1, motor2, motor3) one after another within a 35-second window, with built-in handling for motor faults, partial resets, and a full reset. The timing is preserved even during fault conditions using an offset mechanism.

⏱️ _**Timer and Motor Sequence**_

- A TON timer (motor_timer) runs for 35 seconds.
- The current elapsed time is tracked using motor_et, which adds the motor_timer.ET and any offset_time from previous fault interruptions.
- Based on the value of motor_et, motors are enabled sequentially:
  - 0–5s: All motors OFF
  - 5–15s: motor1 ON
  - 15–25s: motor2 ON
  - 25–35s: motor3 ON
- LEDs associated with each motor (motorX_led) mirror their ON/OFF states.

🚨 **Fault Handling**

- If a motor fault (motorX_fault) is detected:
  - The corresponding motor is turned OFF.
  - Its LED is also turned OFF.
  - Fault_led is switched ON.
  - The elapsed time is stored into offset_time to pause the sequence at the right moment.
- Once the fault clears and the respective reset_motorX is TRUE:
  - That motor can resume.
  - LED turns back ON.
  - Fault_led turns OFF.

🔁 _**Reset Logic**_

- If reset_all is activated:
  - All motors and LEDs are turned OFF.
  - All timers and offsets are cleared.
  - The system restarts fresh.

📞 _**Function Block Calls**_

- At the end of the logic:
  - fbd_call() and ld_call() are triggered — these are references to the same program written in FBD and LD, respectively.

🔧 **Tools Used**

_**Platform:**_ Beckhoff TwinCAT 3.1

_**Language:**_ Structured Text (ST)

🛠️ **Tools Needed to Simulate**

- TwinCAT XAE (Extended Automation Engineering) environment
- Weekly runtime license (valid for 7 days, can be renewed)
  
📌 **Notes**

- Code is provided in 'motor sequence st.txt'.
- No output is shown, as this is a syntax and logic practice file.
- The logic is replicated in FBD and LD, but written separately with their own nuances.

