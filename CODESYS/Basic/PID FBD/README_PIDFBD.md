🎛️ **PID Control Using FBD Block** 

This project demonstrates the use of a PID (Proportional-Integral-Derivative) controller in Function Block Diagram (FBD) format in CODESYS to control motor speed based on pressure feedback.

⚙️ **Control Logic Summary**

- PID Block Name: PID_0
- Control Objective: Maintain motor speed based on pressure input.
- Control Type: Closed-loop automatic control (Manual mode enabled for testing).

🔌 **Input Signals**

- _ACTUAL:_ Input from Pressure_sensor (measured value)
- _SET_POINT:_ Desired pressure set via operator_input
- _KP:_ Proportional Gain (proportional_gain)
- _TN:_ Integral Time (in seconds)
- _TV:_ Derivative Time (in seconds)
- _Y_MANUAL:_ Manual override value (disabled here)
- _Y_OFFSET:_ Output offset (set to 0)
- _Y_MIN:_ Minimum output limit (set to 0)
- _Y_MAX:_ Maximum output limit (set to 500)
- _MANUAL:_ Mode selector – set to TRUE (manual mode)
- _RESET:_ Reset the PID block

🔋 **Output**

- _Y:_ Output to motor_speed
- _LIMITS_ACTIVE:_ Signals limit violations (optional)
- _OVERFLOW:_ Signals internal overflows (optional)

🔧 **Tools Used**

- _**Platform:**_ CODESYS Simulation
- _**Language:**_ Function Block Diagram (FBD)
  
🛠️ **Tools Needed to Simulate**

- CODESYS Control Win SysTray (x64)
- CODESYS Gateway SysTray (x64)

📌 **Notes**

- This is useful in systems where maintaining a process variable (e.g., pressure, temperature) is critical.
- The PID controller continuously adjusts the motor_speed to match the setpoint based on feedback from the pressure sensor.
