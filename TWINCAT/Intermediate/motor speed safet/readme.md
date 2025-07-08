🛡️ **Motor Speed Monitoring with Safety Logic (WIP)**

This project demonstrates a simple setup for monitoring motor speed using analog current input and enforcing safe operating limits through a TwinCAT Safety PLC block. The system is split into two independent parts for now:

  - Safety Logic using safeLimit, safeAnd, and safeRs blocks in the TwinSAFE Editor
  - PLC Logic written in Structured Text (ST) to scale and limit the analog input and control the motor accordingly

The goal is to ensure that only values within the defined safe range are accepted and used for motor operation.

🧩 **Logic Description**

✅ _**Safety Logic**_

- safeLimit block checks if the analog input falls between a predefined minimum and maximum limit (0–5000).
- If the condition is valid and a manual reset is pressed, safeAnd outputs TRUE.
- safeRs latches this signal and enables the motor output (RsOut).
  
  _Mapped variables:_

  - input_value: Analog sensor signal
  - manual_reset: Digital input for safety reset
  - motor: Digital output to enable motor when safe conditions are met

🔧 _**PLC Logic (Structured Text)**_

  -  Scales the 4–20 mA analog current input to an RPM value between 0–5000
  -  Caps the RPM value between 1000 and 5000 before converting it to a UINT for actuator control

🔧 **Tools Used**

Platform: Beckhoff TwinCAT 3.1

Language: Structured Text (ST) for motor speed calculation. TwinSAFE Safety Function Blocks for safety control


🛠️ **Tools Needed to Simulate**

- TwinCAT XAE (Extended Automation Engineering) environment
- Weekly runtime license (valid for 7 days, can be renewed)
- TwinSAFE Configuration
- EL Safety IOs simulated via FSOUT / analog mapping

📌 **Notes**

- The safety and PLC logics currently run independently for test purposes.
- Both components are functional but not yet integrated in a single controller project.
- Future plan: Integrate safety and motor logic fully within a common simulation environment using a unified PLC-Safety mapping.
