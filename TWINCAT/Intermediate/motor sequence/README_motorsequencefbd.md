⚙️ **Motor Sequential Control – Functional Block Diagram**

This implementation of the motor sequence logic is designed using the Function Block Diagram (FBD) programming language in TwinCAT. It mirrors the logical flow of the ST and LD implementations while leveraging FBD's ability to visually represent control flows and data connections.

🧩 **Logic Description**

The logic cycles three motors (motor1, motor2, motor3) one after another within a 35-second window, with built-in handling for motor faults, partial resets, and a full reset. The timing is preserved even during fault conditions using an offset mechanism.

🧮 **Key Components Used**

- _**TON (On-Delay Timer)**_: Used to implement the main motor timer (`main_motor_timer`).
- _**Logical Blocks (AND, OR, etc.)**_: Used to implement conditions for motor start, fault detection, reset, and limit checks.
- _**Comparison Blocks (GE, LT, etc.)**_: To check `et_motor` against specific thresholds for various limit conditions.
- _**MOVE Blocks**_: Used to transfer timer ET value into offset and `et_motor` logic.

⚙️ **Execution Logic Summary**

  1. **Motor Timer Enable Logic**
  - The `main_motor_timer` is activated based on a combination of start push button (`start_pb`), stop condition (`stop_pb`), fault flags (`m1_fault`, `m2_fault`, `m3_fault`), and the state of `main_motor_timer.Q`.
  - A `GE` block ensures that the timer runs only if `et_motor < T#35s`, ensuring timeout is handled.

  2. **Offset Handling**
  - A `MOVE` block transfers the timer value (`ET`) into an `offset` when faults occur.

  3. **ET Calculation**
  - The effective `et_motor` value is calculated by summing the current timer value (`ET`) and the offset value.
  - This value is then compared across various thresholds to evaluate limit levels.

 ⏱️ **Limit Check Zones**
 
- _**Low Limit**:_ `et_motor >= T#5S` AND `< T#15S`
- _**Medium Limit**_: `et_motor >= T#15S` AND `< T#25S`
- _**High Limit**:_ `et_motor >= T#25S` AND `< T#35S`

These checks are implemented directly using stacked `AND` and `GE/LT` comparison blocks within the same chain, making use of FBD's visual flow to avoid multiple Boolean flags.


🔄 **Reset Conditions**

  1. **Fault Reset (Reset All)**
  - When `reset_all` is activated:
    - `offset := T#0S`
    - `et_motor := T#0S`
    - All fault flags and individual resets are cleared.

  2. **Individual Resets**
  - When any of `reset_m1`, `reset_m2`, or `reset_m3` is triggered:
    - All three faults (`m1_fault`, `m2_fault`, `m3_fault`) are cleared.

  3. **Timer Done (Q = TRUE)**
  - When `main_motor_timer.Q` becomes `TRUE`:
    - All faults and resets are cleared.
    - `offset` and `et_motor` are reset to 0.
    - The `main_motor_timer.PT` is reloaded to `T#35S`.

  4. **Reset Limit Check (Post 35s)**
  - If `et_motor >= T#35S` and `reset_limit_check` is active:
    - `offset := T#0S`
    - `et_motor := T#0S`

🧠 **Permanent Rung Logic (Unique to LD & FBD)**

- In LD and FBD only, the final rung contains always-true logic (1) connected to execute and handles advanced resets and fault management
- This ensures:
  - Timers and faults are synced correctly
  - The system doesn’t restart in a faulty or halfway state
  - Resets don't leave stale flags in memory

🔧 **Tools Used**

_**Platform:**_ Beckhoff TwinCAT 3.1

_**Language:**_ Ladder Diagram (LD)

🛠️ **Tools Needed to Simulate**

- TwinCAT XAE (Extended Automation Engineering) environment
- Weekly runtime license (valid for 7 days, can be renewed)

📌 **Notes**

- _Efficient Block Usage:_ By reusing inputs and chaining logical blocks, FBD offers a clean and intuitive flow while maintaining the flexibility of ST.

- _Hybrid Inspiration:_ This FBD logic draws from both ST and LD approaches — it adopts ST’s compact logic expression style and LD’s structured rung evaluation with an always-true execution network.

