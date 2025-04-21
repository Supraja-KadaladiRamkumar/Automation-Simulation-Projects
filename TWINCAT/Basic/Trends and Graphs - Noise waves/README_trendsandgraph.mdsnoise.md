📈 **Noise Waves Trend Plot**

This project focuses on simulating and visualizing noise signals using Structured Text (ST) in TwinCAT 3. Unlike traditional I/O-based process simulations, this task primarily revolves around time-driven signal generation and graphical representation using the YT (Measurement) project.

🧩 **Logic Description**

This project simulates three types of noise signals — pure noise, bounded noise, and white noise. These signals help test system robustness, signal processing features, and HMI visualization under random input conditions. The noise signals are generated within a 200ms time interval using a pseudo-random number generator based on the linear congruential method.

_**Key variables:**_

- _seed:_ Pseudo-random generator base value
- _random_value:_ Scaled value from 0.0 to 1.0
- _amplitude:_ Adjustable amplitude for noise scaling
- _frequency:_ Frequency value for white noise's sine component

📉 **Trend Observation**

Each type of noise signal is displayed in the YT Scope with a unique background color:

🔹 _**Pure Noise**_
- Raw unbounded random signal scaled by amplitude
- Simulates chaotic sensor signals or electrical interference

🔹 _**Bounded Noise**_
- Random values limited to 0–5.0 range
- Represents a more controlled random signal — useful for simulations where values must stay within practical limits

🔹 _**White Noise**_
- Combination of a sinusoidal wave and random fluctuation
- Simulates more realistic analog signals with both pattern and distortion (e.g., noisy temperature or vibration signals)

Each signal updates approximately every 200ms.

🔧 **Tools Used**

_**Platform:**_ Beckhoff TwinCAT 3.1

_**Language:**_ ST (Structured Text)

🛠️ **Tools Needed to Simulate**

- TwinCAT XAE (Extended Automation Engineering) environment
- YT (Measurement) Project for trend visualization
- Weekly runtime license (valid for 7 days, can be renewed)
  
📌 **Notes**

- Trend graphs are useful for monitoring variables over time — and in TwinCAT, this is best achieved using the built-in YT (Time-based Measurement) feature, which allows real-time logging and plotting of tags without the need for an HMI.
- Code is provided in 'noise waves trends st.txt'.
- All noise signals share the same random seed to ensure synchronized generation.
