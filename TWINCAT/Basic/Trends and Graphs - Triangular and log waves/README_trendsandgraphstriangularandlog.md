📈 **Triangle + Logarithmic Wave Trend**

This project focuses on simulating and visualizing triangular and log waveform trend using Structured Text (ST) in TwinCAT 3 using a single timer logic. Unlike traditional I/O-based process simulations, this task primarily revolves around time-driven signal generation and graphical representation using the YT (Measurement) project.

🧩 **Logic Description**

The triangle signal resets periodically to create a peak-trough pattern, while the logarithmic wave shows a steady increase with decreasing slope.

📊 **Trend Observation – Triangle + Logarithmic Waves**

_**Triangle Wave:**_

- Periodically oscillates between 0 and max amplitude.
- Has a clean linear rise and fall, showing uniform slope.
- Used to simulate periodic analog signals with symmetry.

_**Logarithmic Wave:**_

- Begins with a steep rise, gradually flattening.
- Demonstrates classic log growth behavior, useful in modeling real-world signals that grow fast and then stabilize (e.g., sensor drift or temperature rise).

 🔧 **Tools Used**
 
_**Platform:**_ Beckhoff TwinCAT 3.1

_**Language:**_ ST (Structured Text)

🛠️ **Tools Needed to Simulate**

- TwinCAT XAE (Extended Automation Engineering) environment
- YT (Measurement) Project for trend visualization
- Weekly runtime license (valid for 7 days, can be renewed)
  
📌 **Notes**

- Trend graphs are useful for monitoring variables over time — and in TwinCAT, this is best achieved using the built-in YT (Time-based Measurement) feature, which allows real-time logging and plotting of tags without the need for an HMI.
- Code is provided in 'triangular and log waves st.txt'.
- Triangle wave is wrapped using modulo to maintain periodicity.
- The log signal does not reset but continuously grows over time unless reset explicitly.
