📈 **Ramp Signal Trend**

This project focuses on simulating and visualizing a ramp waveform using Structured Text (ST) in TwinCAT 3. Unlike traditional I/O-based process simulations, this task primarily revolves around time-driven signal generation and graphical representation using the YT (Measurement) project.

🧩 **Logic Description**

- The ramp_total increases by 1.0 every 1 second, controlled by an internal time_total timer.
- The counter resets when:
  - ramp_total > max_limit, or
  - reset or stop is triggered.
- Uses a manual timer simulation with T#10MS increments, like before.

📊 **Trend Observation – Ramp Signal**

From the trend image:
- _Signal Behavior:_
  - The green line shows a clean, stepwise linear ramp, increasing steadily.
  - It resets sharply to 0 once it reaches a certain point (~75.0), confirming the effect of ramp_total > max_limit.
- _Visual Notes:_
  - Y-axis: Represents ramp_total.
  - X-axis: Time, spread across one minute.
  - The signal has a sawtooth waveform with smooth upward slope and sudden reset.
  - Each "step" is likely due to screen refresh rate or the plotting interval of ramp_total.

🔧 **Tools Used**

**Platform:** Beckhoff TwinCAT 3.1

**Language:** ST (Structured Text)

🛠️ **Tools Needed to Simulate**

- TwinCAT XAE (Extended Automation Engineering) environment
- YT (Measurement) Project for trend visualization
- Weekly runtime license (valid for 7 days, can be renewed)

📌 **Notes**

- Trend graphs are useful for monitoring variables over time — and in TwinCAT, this is best achieved using the built-in YT (Time-based Measurement) feature, which allows real-time logging and plotting of tags without the need for an HMI.
- Code is provided in 'ramp wave st.txt'.
- Controlled ramp: Nice for simulation and testing analog outputs.
