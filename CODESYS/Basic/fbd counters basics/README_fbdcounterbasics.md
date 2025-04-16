💡 **Turning on lamp with Counter & Functional Blocks (FBD)**

A basic-level project implemented using Function Block Diagram (FBD) logic to control a lamp using an Up-Counter. This example demonstrates how a counter can be used with input conditions to activate an output once a specific count is reached.

🧩 **Logic Description**

_**Network 1:**_ **Up Counter**

  **Inputs:**
  
   _**cu:**_ **(Count Up)**:
 
     AND Block containing the following conditions:
  
    - _Input 1:_ Simulates a sensor detecting an object
    - _Input 2:_ Done bit from the counter (used to stop counting once the target is reached)

 **Reset:**

  - Reset push button to reset the counter to zero
  
**Output:**
  
  - A LED turns ON when the counter reaches its preset value

🔧 **Tools Used**

_**Platform:**_ CODESYS Simulation

_**Language:**_ Ladder Diagram (LD)

🛠️ **Tools Needed to Simulate**

- CODESYS Control Win Systray x64
- CODESYS Gateway Systray x64

📌 **Notes**

This is a beginner-level project created during CODESYS practice to understand counter operations and their interaction with logic gates in simulation.
