📈 **Linear and Square Wave Generator**

This project focuses on simulating and visualizing a linear and square waveforms using Structured Text (ST) in TwinCAT 3. Unlike traditional I/O-based process simulations, this task primarily revolves around time-driven signal generation and graphical representation using the YT (Measurement) project.

🧩 **Logic Description**

This program combines two classic waveforms—linear ramp and square wave—generated simultaneously using a single timer.

_**Timer logic:**_ Simulated using timer_value, incremented every cycle by T#1MS.
  - _Square wave:_ Toggles square_signal on reaching square_time_limit, and switches square_wave between 0.0 and 50.0 accordingly.
  - _Linear ramp:_ Increments linear_value by 1.0 every linear_time_limit. When it hits max_linear, both linear_value and timer_value reset.
    
**_Reset/Stop Logic:_** If either reset or stop is active (and start is not), everything resets:
  - linear_value, square_wave, timer_value → set to 0
  - timer_on → turned off

📊 **Trend Observation – Linear vs. Square Waves**

From the trend image:
- Top Graph (Linear signal – Green Line):
  - Displays a steady upward slope (ramp function).
  - Resets to 0.0 after hitting a peak, creating a sawtooth waveform.
- Bottom Graph (Square signal – Blue Blocks):
  - Alternates between high (50.0) and low (0.0) at regular intervals.
  - Gives a classic digital square wave appearance.
    
⏱ Both signals reset periodically, and their timing is aligned through shared timer logic.

🔧 **Tools Used**

_**Platform:**_ Beckhoff TwinCAT 3.1

_**Language:**_ ST (Structured Text)

🛠️ **Tools Needed to Simulate**

- TwinCAT XAE (Extended Automation Engineering) environment
- YT (Measurement) Project for trend visualization
- Weekly runtime license (valid for 7 days, can be renewed)

📌 **Notes**

- This program is a neat way to simulate two fundamental signals, perfect for:
  - PLC signal testing
  - Animation demos in YT Scope
  - Practicing time-controlled signal generation in real-world automation contexts
- Both waveforms use a single timer instead of separate ones.
- Reset logic helps prevent overflow and maintains predictable behavior.
- Trend graphs are useful for monitoring variables over time — and in TwinCAT, this is best achieved using the built-in YT (Time-based Measurement) feature, which allows real-time logging and plotting of tags without the need for an HMI.
- Code is provided in 'linear and square waves st.txt'.

