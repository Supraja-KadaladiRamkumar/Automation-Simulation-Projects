🌀 **Multiple motor running simulation with Timer & Functional Blocks (FBD)**

This project demonstrates how multiple motors can be operated using latching techniques implemented in Function Block Diagram (FBD) logic. It uses timers, comparators, output latch and both Set-Reset (SR) and Reset-Set (RS) blocks. Each motor behaves based on different input-triggered conditions, simulating various real-world latching scenarios.

🧩 **Logic Description**
_**Network 1:**_ 

- **Inputs:** 
  - Start push button to the timer (preset of 10s)
  - Motor is latched so the process continues even if the button is released
  - Negated Stop push button
  
- **Output:** 
  - Motor turns ON after the timer completes and stays ON until Stop is pressed

_**Network 2:**_ 

- **Inputs:** 
  - Start push button to the timer (preset of 10s)
  - Set input latches the motor even after input is released
  - Negated Stop push button to reset the SR block
  
- **Output:** 
  - Motor turns ON once the Set input is activated and remains ON until Reset is pressed


_**Network 3:**_ 

- **Inputs:** 
  - Reset start push button to the timer (preset of 10s)
  - Set input to latch the output
  - Negated Stop push button to reset the RS block
  
- **Output:** 
  - Motor turns ON after Set input activates and turns OFF immediately when Reset is pressed

🔧 **Tools Used**

- _**Platform:**_ CODESYS Simulation
- _**Language:**_ Ladder Diagram (LD)

🛠️ **Tools Needed to Simulate**

- CODESYS Control Win Systray x64
- CODESYS Gateway Systray x64
  
 📌 Notes

This is a beginner-level project created during CODESYS practice to explore different latching methods and understand how SR, RS, and basic memory blocks behave under simulation.
