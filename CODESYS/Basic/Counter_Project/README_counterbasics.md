**Up-Down Counter Practice (CODESYS)**
This program demonstrates the use of Up, Down, and Up-Down counters in CODESYS using ladder logic. The logic has been split across three rungs, each focusing on different counter functionalities.

🧩**Logic Description**

**_Rung 1: Up Counter_**
- **Inputs:** 
  - `cu`: `up_sensor`
  - `reset`: `reset_up`
- **Output:** 
  - A LED turns ON when the counter reaches its target value.

**_Rung 2: Down Counter (with Load)_**
- **Inputs:**
  - `cu`: `down_sensor`
  - `load`: `load_switch`
- **Output:** 
  - A second LED turns ON as per the down counting logic.

**_Rung 3: Up-Down Counter_**
- **Inputs:**
  - `cu`: `up_sensor_upd`
  - `cd`: `down_sensor_upd`
  - `reset`: `reset_upd`
  - `load`: `load_upd`
- **Output:** 
  - No output connected
  
🔧 **Tools Used**
- **_Platform:_** CODESYS Simulation
- **_Language_:** Ladder Diagram (LD)
  
🛠️ **Tools Needed to Simulate**
  
- CODESYS Control Win Systray x64
- CODESYS Gateway Systray x64

📌 **Notes**
This is a basic-level project created during CODESYS practice to understand different counter types and how they behave during simulation.
