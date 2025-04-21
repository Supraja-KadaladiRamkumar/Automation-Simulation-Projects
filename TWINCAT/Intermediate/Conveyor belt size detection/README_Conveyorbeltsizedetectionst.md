🚧📦 **Object Sorting in Conveyor Belt – – Structured Text (ST)**

This program simulates a basic object sorting system in an industrial process automation setting. Based on sensor input and manual triggers, objects detected on a conveyor belt are sorted into two bins — small or big — depending on defined logic conditions using Structured Text (ST) in TwinCAT. It includes fault detection for delayed manual input.

🧩 **Logic Description**

- The conveyor is activated when the system starts, and remains ON as long as there's no stop signal, fault, reset, or object detected.
- A 10-second timer (conveyor_timer) is started when the conveyor is ON.
- If an object is detected by object_sensor before 10 seconds:
  - A temporary flag temp_object is raised.
  - If manual input is received within the first 5 seconds, temp_manual is set.
- Based on the flags:
  - If temp_manual is TRUE, the object is sorted to bin_small.
  - Else, the object is sorted to bin_big.
- If no manual input is received before the timer expires, a fault_detected flag is triggered.
- On reset or stop, all flags and bin outputs are cleared to return the system to the default state.

📞 **Function Block Calls**

At the end of the logic: fbd_call() and ld_call() are triggered — these are references to the same program written in FBD and LD, respectively.

🔧 **Tools Used**

_**Platform:**_ Beckhoff TwinCAT 3.1

_**Language:**_ Structured Text (ST)

🛠️ **Tools Needed to Simulate**

- TwinCAT XAE (Extended Automation Engineering) environment
- Weekly runtime license (valid for 7 days, can be renewed)
  
📌 **Notes**
- Code is provided in 'conveyor built - size detection st.txt'.
- The logic can be extended for HMI integration later, where object detection and manual classification can be controlled via buttons.
- No output is shown, as this is a syntax and logic practice file.
- The logic is replicated in FBD and LD, but written separately with their own nuances.
