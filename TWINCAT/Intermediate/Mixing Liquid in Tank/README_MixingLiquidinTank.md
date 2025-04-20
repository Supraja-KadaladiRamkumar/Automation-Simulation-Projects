🧪 **Mixing Liquid in Tank – Ladder Logic (LD) + Structured Text (ST)**

This project simulates a liquid mixing process in a tank using a combination of:
- Ladder Logic (LD) for valve and process control
- Structured Text (ST) for calculating tank levels and visual indicators
- A basic HMI interface for toggling between different screens and visualizing process states

🧩 **Logic Description**

This project simulates a 3-phase mixing process in a tank and includes input, mixing, and drain phases, each with its own timers, valves, and screen indicators.

🧠 **Process Phases**

The process is divided into three sequential phases:
- _**Input:**_ Water fills the tank through an input valve. The tank level decreases visually on HMI as the timer progresses.
- _**Mixing:**_ A mixer rotates during the mixing phase. The rotation is calculated based on elapsed time and shown visually.
- _**Drain:**_ The liquid drains through an output valve. The tank level increases again to simulate draining.

🧰 **Control Logic**

_**Ladder Logic (LD):**_

- Controls the ON/OFF state of valves and mixer motor.
- Uses TON timers to sequence the three phases.
- Sets process indicator LEDs and handles screen transitions.

_**Structured Text (ST):**_

- Calculates water_level_percentage during input/drain phases.
- Computes rotation_angle during the mixing phase.
- Uses real-time timer values (ET) for realistic visual feedback.
- Code is provided in 'mixing liquid st code.png'.

💻 **HMI Logic**

- Navigation between input, mixing, and drain screens using toggles.
- Each screen activates a specific LED indicator.
- Relevant valves/motor symbols appear based on the phase.
- Tank level and mixer rotation are visually updated.
⚠️ _Note:_ The HMI is basic due to TwinCAT's limited visualization capabilities. It is intended for simulation and understanding of the process rather than high-end interaction.

🔧 **Tools Used**

_**Platform:**_ Beckhoff TwinCAT 3.1

_**Language:**_ Ladder Diagram (LD)

🛠️ **Tools Needed to Simulate**

- TwinCAT XAE (Extended Automation Engineering) environment
- Weekly runtime license (valid for 7 days, can be renewed)
  
📷 **Visual Reference**

Screenshots of the output are attached, including before simulation and the simulation outputs for each phase of the process.

📌 **Notes**

- ST code ensures dynamic behavior and calculations.
- While TwinCAT provides basic HMI features, this project demonstrates screen switching and real-time updates using available elements.
