🚦 **Traffic Light Control – Structured Text (ST)**

This program simulates a traffic light control sequence with three lights: Green, Yellow, and Red, cycling based on elapsed time. Two different methods are used:

- A basic ST approach using IF conditions.
- An enum-based approach using a CASE statement for better state management and readability.

🧩 **Logic Description**

1. _**Standard ST Method**_
  - A TON timer (traffic_timer) runs for 20 seconds.
  - The elapsed_time is derived from traffic_timer.ET.
  - Light transitions:
    - Green: On at start and remains until 7s.
    - Yellow: From 7s to 10s.
    - Red: From 10s to 20s.
  - When the timer completes (i.e., traffic_timer.q = TRUE), the sequence resets to Green.

2. _**Enum-Based Method with CASE**_
  - A user-defined ENUM (traffic_enuma) represents the current state: .green, .yellow, .red.
  - Cleaner control flow using a CASE statement.
  - State transitions:
    - Green → Yellow (after 7s)
    - Yellow → Red (after 10s)
    - Red → Green (after 20s and timer resets)
  - Provides a more robust way to manage transitions, especially if the state machine becomes more complex later.

🚨 **Stop & Reset Handling (Enum Method)**

- If either stop_enum or off_enum is triggered:
  - All lights are turned OFF
  - State resets to .green
  - Timer (elapsed_time_enum) is reset to T#0S

📞 **Function Block Calls**

At the end of the logic: fbd_call() and ld_call() are triggered — these are references to the same program written in FBD and LD, respectively.

🔧 **Tools Used**

_**Platform:**_ Beckhoff TwinCAT 3.1

_**Language:**_ Structured Text (ST)

🛠️ _**Tools Needed to Simulate**_

- TwinCAT XAE (Extended Automation Engineering) environment
- Weekly runtime license (valid for 7 days, can be renewed)
  
📌 **Notes**

- Code is provided in 'traffic light st.txt'.
- No output is shown, as this is a syntax and logic practice file.
- The logic is replicated in FBD and LD, but written separately with their own nuances.
- The standard ST method is simple and straightforward.
- The enum-based method is more scalable and safer for future enhancements (e.g., pedestrian crossing, blinking modes).


