🔁 **Timers & Counters for Multi-Output Control (ST)**

This project demonstrates the use of various Timers and Counters to control different outputs such as a motor, fan, and conveyor belts. It’s implemented in Structured Text (ST) in CODESYS.

🧩 **Logic Description**

**Pulse Timer (TON):**
  - _pulse_timer:_ Activates when start_pulse is TRUE and remains ON for 5 seconds.
  - _Outputs:_
    - elapsed_pulse: Elapsed time since activation.
    - out: TRUE during the timer duration.

**ON-Delay Timer (TON):**
  - _on_timer:_ Starts when start_on is active.
  - _Output:_
    - motor: Turns ON after a delay of 5 seconds.

**OFF-Delay Timer (TON):**
  - _off_timer:_ Starts counting when start_off is activated.
  - _Output:_
    - fan: Turns ON after 5 seconds of delay.

**Count Up (CTU):**
  - _count_up:_ Increments on inp_up, resets on reset_inp.
  - _Output:_
    - belt1: Turns ON when counter reaches preset value 3.

**Count Down (CTD):**
  - _count_down:_ Decrements on inp_down, loads preset value 3 on load_inp.
  - _Output:_
    - belt2: Turns ON when counter reaches 0.

**Count Up/Down (CTUD):**
  - _count_up_down:_ Combines up/down count logic using inp_up, inp_down, reset_inp, and load_inp.

🔧 **Tools Used**

_**Platform:**_ CODESYS Simulation
_**Language:**_ Structured Text (ST)

🛠️ **Tools Needed to Simulate**

- CODESYS Control Win SysTray (x64)
- CODESYS Gateway SysTray (x64)

📌 **Notes**

- This project is useful for simulating control systems that involve timed sequences and inventory tracking.
- Counters can be adapted for batch processing, and timers help ensure delayed or pulse-based activation of outputs.
- The Count Up/Down block is particularly useful in systems with inflow and outflow tracking.
- Code is provided in 'basic st.txt'.
- No output is shown, as this is a syntax and logic practice file.


