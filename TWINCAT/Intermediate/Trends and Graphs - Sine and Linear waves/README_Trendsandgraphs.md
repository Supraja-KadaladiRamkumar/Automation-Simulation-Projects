📈 **Delayed Linear Ramp and Sine Wave**

This project focuses on simulating and visualizing a linear and sine waveforms using Structured Text (ST) in TwinCAT 3. Unlike traditional I/O-based process simulations, this task primarily revolves around time-driven signal generation and graphical representation using the YT (Measurement) project.

🧩 **Logic Description**

This logic combines two distinct signal patterns triggered by different start/reset conditions:
- A linear ramp signal (temp) that begins after a delay and stops upon reaching a defined maximum.
- A sine wave signal (total) that updates in discrete time steps to simulate periodic oscillation.

**Temp Signal (Linear Ramp with Delay):_**_

- The temp value begins increasing linearly by 1.5 units once a preset delay_time elapses.
- The increment continues until temp >= max_temp, at which point the loop ends (loop_done := TRUE).
- The whole loop resets on reset or stop, bringing temp back to zero.

_**Total Signal (Sine Wave):**_

- Uses a time-driven sine update: every 2 seconds (T#2S), the sine variable increases by 0.1 radians.
- total := 20.0 + 5.0 * SIN(sine) gives a smooth sine wave oscillating between 15 and 25 units.
- Resets clear the accumulated sine and time values.

📊 **Trend Observation – Linear Ramp and Sine Wave**

- Temp will appear as a flat line initially (during delay), followed by a linear slope until it saturates at the max_temp.
- Total exhibits a smooth sine wave, gradually oscillating as time progresses.

🔧 **Tools Used**

_**Platform:**_ Beckhoff TwinCAT 3.1

_**Language:**_ ST (Structured Text)

🛠️ **Tools Needed to Simulate**

- TwinCAT XAE (Extended Automation Engineering) environment
- YT (Measurement) Project for trend visualization
- Weekly runtime license (valid for 7 days, can be renewed)
  
📌 **Notes**

- Trend graphs are useful for monitoring variables over time — and in TwinCAT, this is best achieved using the built-in YT (Time-based Measurement) feature, which allows real-time logging and plotting of tags without the need for an HMI.
- Code is provided in 'Sine and Linear waves st.txt'.
- Ideal for simulating temperature rise or PID input response with periodic reference changes.
