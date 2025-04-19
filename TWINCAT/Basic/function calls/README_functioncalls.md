💡 **Start-Stop Light Control/ Function calls basics**

🧩 **Logic Description**

This is a basic TwinCAT 3.1 project that demonstrates how to modularize logic using POUs (Program Organization Units). The goal is simple: control a light (LED) using Start and Stop inputs, implemented in both Ladder Diagram (LD) and Function Block Diagram (FBD) for comparison.

 - _**Main Program**_
   
   - Calls two child POUs: `fbd_call()` and `ladder_logic_call()`.
   - `start` and `stop` inputs are passed to the LD POU.
   - Output `light` is returned from LD and assigned in the main program.

- _**Ladder Logic (LD)**_
   - Implements a classic Set/Reset latch:
       - **Set** when `start` is pressed.
       - **Reset** when `stop` is pressed.
   - The `light` stays ON until `stop` is activated again.
 
- _**Function Block Diagram (FBD)**_
   - Achieves the same latch logic differently:
   - Uses an AND gate with inputs: `start`, latched `light`, and `NOT stop`.
   - Output goes to `light`, producing a latched effect.
   - Great for understanding logic flow using gates.
 
🔧 **Tools Used**

_**Platform:**_ Beckhoff TwinCAT 3.1

_**Language:**_ POUs written in LD and FBD. Main program in Structured Text

🛠️ **Tools Needed to Simulate**

- TwinCAT XAE (Extended Automation Engineering) environment
- Weekly runtime license (valid for 7 days, can be renewed)

📌 **Notes**

- A simple, clean example of how LD and FBD can be used to model the same logic.
- Demonstrates the power of modular POUs in TwinCAT.
