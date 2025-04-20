📈 **Exponential Trend Plot**

This project focuses on simulating and visualizing a exponential waveform trend using Structured Text (ST) in TwinCAT 3. Unlike traditional I/O-based process simulations, this task primarily revolves around time-driven signal generation and graphical representation using the YT (Measurement) project.

🧩 **Logic Description**

This program demonstrates an exponential signal generator using a simple cyclic logic. The variable expo_value is multiplied repeatedly by a base_value at regular time intervals (timer_limit). Once it exceeds the max_limit, it resets to 1.0 and starts over.

_**Key variables:**_

- expo_value: Current signal value (starts from 1.0)
- base_value: Constant multiplier (e.g., 2.0)
- timer_limit: Interval between each multiplication (e.g., 100 ms)
- max_limit: Value cap before reset
- timer_on, timer_value: Handle the timing logic

📊 **Trend Observation – Exponential Waveform**

The YT Scope plot visualizes an exponential growth pattern over time:
- The expo_value grows by multiplying itself with a constant factor.
- The graph shows the classic steep rise of exponential curves.
- After crossing a threshold (max_limit), it resets and starts over.
- This setup mimics real-world systems like chain reactions, recursive processes, or financial growth curves.
  
🔧 **Tools Used**

_**Platform:**_ Beckhoff TwinCAT 3.1

_**Language:**_ ST (Structured Text)

🛠️ **Tools Needed to Simulate**

- TwinCAT XAE (Extended Automation Engineering) environment
- YT (Measurement) Project for trend visualization
- Weekly runtime license (valid for 7 days, can be renewed)
  
📌 **Notes**

- Trend graphs are useful for monitoring variables over time — and in TwinCAT, this is best achieved using the built-in YT (Time-based Measurement) feature, which allows real-time logging and plotting of tags without the need for an HMI.
- Code is provided in 'exponential trend st.txt'.
- This logic avoids overflow by resetting the exponential value before it gets too large.
- The signal appears stepwise in the trend due to fixed sampling intervals.
- Resetting is handled both when the signal exceeds the limit and through external commands (reset or stop).
