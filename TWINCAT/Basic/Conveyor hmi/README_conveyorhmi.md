📦 **HMI Conveyor Control**

This project simulates a simple conveyor control system using Function Block Diagram (FBD) in TwinCAT 3. The setup includes basic start/stop control, a speed adjustment via potentiometer, and a visual representation of a moving object (box) on the HMI.

🧩 **Logic Description**

⚙️ **Step-by-Step Logic Flow:**

  1. _**Start/Stop Control**_
    - The conveyor is activated using a logical AND condition between start and NOT stop.
    
  2. _**Enable Calculation**_
    - A TON (On-delay Timer) introduces a delay before enabling the position calculation.
    - The timer is triggered by both the conveyor being active and the timer’s own output being LOW.

  3. _**Speed Calculation**_
    - Once calc_enable is TRUE, the speed is calculated from the slider_speed (potentiometer input), multiplied by 10, then divided by 100 to normalize.

  4. _**Position Update**_
    - The calculated value is added to the current conveyor position to create a new temporary position.
    - This is converted to an integer value for display purposes.

  5. _**Looping Motion**_
    - The new conveyor position is wrapped using a MOD operation to cycle within bounds defined by (max_lim + 1).

  6. _**Position Move**_
    - Finally, the new position is moved back into conveyor_pos, completing the loop.

🖥️ **HMI Interface**

- _**Start & Stop Buttons:**_ Activate or halt the conveyor logic.
- _**Potentiometer Dial:**_ Adjusts the conveyor speed (slider_speed).
- _**Box Movement:**_ A symbolic object on the screen moves to the right based on the value of visual_conv from the logic. This is bound to the X-position of the box.

🔧 **Tools Used**

_**Platform:**_ Beckhoff TwinCAT 3.1

_**Language:**_ Function Block Diagram (FBD)

🛠️ **Tools Needed to Simulate**

- TwinCAT XAE (Extended Automation Engineering) environment
- Weekly runtime license (valid for 7 days, can be renewed)

📌 **Notes**
- The visual elements in this version of TwinCAT 3 are quite limited, so the appearance of the conveyor and boxes is rudimentary.
- Despite the basic visuals, the program demonstrates a working model of real-time speed control, position tracking, and motion cycling — ideal for training or testing logic design.

