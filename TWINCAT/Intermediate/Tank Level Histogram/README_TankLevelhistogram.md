🧪 **Tank Level Histogram**

This program captures and visualizes tank input, output, and level trends over multiple cycles using histograms. It supports user-controlled data submission and includes an overflow alarm mechanism.

🧩 **Logic Description**

- Upon each user submission (via HMI), sensor input and output values are stored in arrays.
- The difference between input and output values is cumulatively added to compute tank level per cycle.
- If the tank level exceeds the maximum or 10 entries are reached, an overflow alarm is triggered, hiding input fields.
- Reset clears all arrays and alarms, allowing a fresh round of monitoring.

📈 **Trend Observation**

_**3-Bar Tracking:**_
  - _Input Valve Bar_ – Tracks values submitted for incoming flow
  - _Output Valve Bar_ – Shows how much was drained
  - _Tank Level Bar_ – Indicates cumulative fill status
This allows quick visual inspection of imbalance or overflow risks across input/output cycles.

🖥️ **HMI Overview**

_**Variable Screen:**_
  - Input fields for sensor values
  - Submit button to log readings
  - A toggle button to switch to the histogram view

_**Histogram Screen:**_
  - Displays the three bars for input, output, and tank level
  - Includes an overflow LED indicator
  - A back button to return to variable input screen

🔧 **Tools Used**

_**Platform:**_ Beckhoff TwinCAT 3.1

_**Language:**_ Structured Text (ST)

🛠️ **Tools Needed to Simulate**

- TwinCAT XAE (Extended Automation Engineering) environment
- Weekly runtime license (valid for 7 days, can be renewed)
  
📌 **Notes**

- Code is provided in 'tank level histogram st.txt'.
- Overflow alert helps in limiting operations when critical limits are reached.
  
