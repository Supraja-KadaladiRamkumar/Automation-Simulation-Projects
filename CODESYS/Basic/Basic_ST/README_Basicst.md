💡 **Basic LED ON/OFF Control using Set/Reset & Latching (ST + Function Blocks)**

This project demonstrates multiple ways to control an LED using Structured Text (ST) and Function Blocks in CODESYS. It includes direct logic, latching, and different forms of Set/Reset operations to illustrate memory behavior.

🧩 **Logic Description**

- **Direct ON/OFF Logic:**
  - led: Turns ON when on is pressed and off is not active.
  - light: Uses latching logic — remains ON after on is pressed, and turns OFF only when off is triggered.

- **Set/Reset Coil Logic (using S and R):**
  - new_light: Set coil activates with on, Reset coil deactivates with off.
  - new_light2: A variation where Reset happens on on, and Set on off.

- **SR & RS Function Blocks:**
  - set_reset: SR flip-flop function block sets led2 with on and resets with off.
  - reset_set: RS flip-flop function block sets led3 with on and resets with off.
 
🔧 **Tools Used**

- _**Platform:**_ CODESYS Simulation
- _**Language:**_ Structured Text (ST)

🛠️ **Tools Needed to Simulate**

- CODESYS Control Win SysTray (x64)
- CODESYS Gateway SysTray (x64)

📌 **Notes**

- This is a beginner-level practice project created to explore various Set/Reset and latching mechanisms.
- Useful for understanding how memory elements behave with different types of logic structures.
- Code is provided in 'basic st.txt'.
- No output is shown, as this is a syntax and logic practice file.
