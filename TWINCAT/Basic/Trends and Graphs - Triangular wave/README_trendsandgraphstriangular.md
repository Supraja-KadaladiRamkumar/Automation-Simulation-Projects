📈 **Triangular Trend Graph**

This project focuses on simulating and visualizing a triangular waveform trend using Structured Text (ST) in TwinCAT 3. Unlike traditional I/O-based process simulations, this task primarily revolves around time-driven signal generation and graphical representation using the YT (Measurement) project.

🧩 **Logic Description**

At the core of the project is an ST-based simulation of a triangular waveform.
  
  **_Key points:_**
  - total is the key value plotted on the YT graph.
  - total_increase and total_decrease create the triangular up-down pattern.
  - A T#1MS timer simulates time progression.
  - The YT measurement project will read total to generate a live graph.

📊 **Trend Observation – Triangular Waveform**

The attached screenshot illustrates the triangular trend generated using Structured Text logic in TwinCAT. The variable total is plotted in real time using the YT Scope.

🔍 **Key Observations:**

- The waveform increases and decreases linearly over time, forming a sharp triangular pattern.
- The signal ramps up until it hits the max_value, then ramps down toward the min_value, before repeating.
- This pattern is created by incrementing or decrementing the total value at fixed time intervals (2.5 units every cycle).
- The period and amplitude of the triangle are directly controlled by the values of timer_limit, min_value, and max_value.

🔧 **Tools Used**

_**Platform:**_ Beckhoff TwinCAT 3.1

_**Language:**_ ST (Structured Text)

🛠️ **Tools Needed to Simulate**

- TwinCAT XAE (Extended Automation Engineering) environment
- YT (Measurement) Project for trend visualization
- Weekly runtime license (valid for 7 days, can be renewed)

📌 **Notes**

- Trend graphs are useful for monitoring variables over time — and in TwinCAT, this is best achieved using the built-in YT (Time-based Measurement) feature, which allows real-time logging and plotting of tags without the need for an HMI.
- Code is provided in 'triangular wave hmi st.txt'.
- This kind of simulated signal is also useful in PID control tuning.
