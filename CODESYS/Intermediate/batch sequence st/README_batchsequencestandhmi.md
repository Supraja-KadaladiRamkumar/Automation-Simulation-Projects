🔂 **Temperature Control Process with Heating, Mixing, and Cooling/Batch sequence process**

This program simulates a temperature-based process that follows a cycle of **heating → mixing → cooling**, implemented using timers and conditional blocks in CODESYS. 

🧩 **Logic Description**

The simulation models a real-world industrial heating and cooling cycle. Each stage transitions smoothly into the next, and the system simulates changes in temperature dynamically using control logic.

🧮 **Key Functional Blocks:**

1. _**Heating Phase**_
   - Begins when `start` is pressed and `stop` is NOT pressed.
   - A timer (`on_timer`) triggers gradual temperature increase after a 5s delay.
   - Heating continues until the `temp_reading` exceeds the `set_point`, after which a break condition and an alarm are activated.

2. _**Mixing Phase**_
   - Starts once heating is complete.
   - A 10s mixing timer runs, turning ON the `mixer` and turning OFF the alarm.
   - Once mixing completes, the system transitions to the cooling phase.

3. _**Cooling Phase**_
   - The temperature (`cooling_temp`) begins to reduce once mixing ends.
   - A `cooling_timer` handles cooling duration.
   - Cooling continues until the temperature drops below `cooling_SP`.
   - A `cool_reset_timer` ensures a pause before resetting cooling status.

🔧 **Tools Used**

_**Platform:**_ CODESYS Simulation

_**Language:**_ Structured Text (ST)

🛠️ **Tools Needed to Simulate**

- CODESYS Control Win Systray x64
- CODESYS Gateway Systray x64
  
📷 **Visual Reference**

Screenshots of the HMI are attached, including the visualization layout before simulation and the simulation outputs for all process cycles.

📌 **Notes**

- **_Future Improvisations:_**
  - **Introduce timers inside loops** to simulate a smoother and more realistic temperature rise or fall (currently it's instant once condition is met).
  - **Add a process cycle loop** – once cooling is done, the cycle should automatically restart unless `stop` is pressed.
- Code is provided in 'batch sequence ST.txt'.
