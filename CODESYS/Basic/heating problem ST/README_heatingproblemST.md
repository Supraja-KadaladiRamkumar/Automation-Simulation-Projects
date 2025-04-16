♨️ **Heater Control using ON-Delay Timer (ST)**

This basic project demonstrates the use of an ON-delay timer to control a heating element in Structured Text (ST) in CODESYS.

🧩 **Logic Description**

- **Inputs:**
  - _start:_ Initiates the heating process.
  - _stop:_ Halts the process when active.

- **Timer:**
  - _on_timer:_ An ON-delay timer is activated when temp_sensor condition is met (start pressed and stop not active).
  - The timer waits for 5 seconds (T#5S) before activating its output.

- **Output:**
  - _heating_element:_ Turns ON only after the 5-second delay, simulating a controlled warm-up period.
 
🔧 **Tools Used**

- _**Platform:**_ CODESYS Simulation
- _**Language:**_ Structured Text (ST)

🛠️ **Tools Needed to Simulate**

- CODESYS Control Win SysTray (x64)
- CODESYS Gateway SysTray (x64)

📌 **Notes**

- This simple logic introduces how ON-delay timers work in ST.
- It's useful for controlling time-based operations, especially in processes where a delay is required before switching on an output.
- Can be extended to more complex heating or motor control applications.
- Code is provided in 'Heating problem st.txt'
- No output is shown, as this is a syntax and logic practice file

