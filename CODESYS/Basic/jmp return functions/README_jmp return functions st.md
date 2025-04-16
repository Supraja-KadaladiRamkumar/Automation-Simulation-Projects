🔁 **Conditional Logic & Function Block for Arithmetic Operations**

This project demonstrates conditional branching using IF, JMP, and RETURN statements, along with a custom function block for basic arithmetic operations in a structured programming environment (e.g., ST in CODESYS).

🧩 **Logic Description**

- The output out is modified depending on the value of n:
  - If n = 5: increment out by 1.
  - If n = 0: jump to a labeled section to add 2 to out.
  - If n = 1: perform a return without affecting the output (out := out + 0).

- The program uses a function block (func) that performs:
  - Subtraction: sub_result := num1 - num2
  - Division: div_result := num1 / num2

- The function is invoked with inputs x and y and results are captured in sub_res and div_res.

🔧 **Tools Used**

_**Platform:**_ CODESYS Simulation

_**Language:**_ Structured Text (ST)

🛠️ **Tools Needed to Simulate**

- CODESYS Control Win SysTray (x64)
- CODESYS Gateway SysTray (x64)

📌 **Notes**

- Code is provided in 'jmp return functions.txt'.
- No output is shown, as this is a syntax and logic practice file.
- This structure is ideal for demoing conditional logic flow and basic function block integration within PLC programs.
