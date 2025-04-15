 # ⚙️ Arithmetic, Comparison & Logic Operators (Ladder Logic with Function Blocks)
This project demonstrates how to use some of the **arithmetic**, **comparison**, and **logic** operators in **Ladder Logic (LD)** using **function blocks** in CODESYS.

🧩 **Logic Description** 

**Rung 1: `R_TRIG + ADD`**
-On rising edge of `Enable`, value is incremented by 1   

**Rung 2: `ADD + GT`**
- Adds `Inp` and `lim`; checks if result > 10  

**Rung 3: `XOR`**
- Performs logical XOR between `X` and `Y`  

**Rung 4: `SEL`**
- Outputs `num1` or `num2` based on control bit `C`  

**Rung 5: `MUX`**
- Selects among multiple numbers based on `B` input 

**Rung 6: `R_TRIG + ADD`**
-  Constrains `test` value between lower (0) and upper (100) limits 

Each function block uses standard EN/ENO logic for execution control, and variables are defined for input/output clarity.


🔧 **Tools Used**
- **Platform**: CODESYS Simulation
-**Language**: Ladder Diagram (LD)

🛠️ **Tools Needed to Simulate**
- CODESYS Control Win Systray x64
- CODESYS Gateway Systray x64

📌 **Notes**
- `R_TRIG` is used to trigger `ADD` only once per Enable rising edge — avoids continuous addition
- Function blocks like `MUX`, `SEL`, and `LIMIT` help simulate conditional behavior typically done via structured logic
- Useful to understand how LD can incorporate structured decision-making using built-in function blocks
