📦 **Conveyor Belt Control with Object Counting & Defect Handling (ST)**

This project simulates the control of a forward and reverse conveyor belt system. Implemented using Structured Text (ST) in CODESYS, it tracks the number of objects processed, handles defective items, and manages the conveyor flow accordingly.

🧩 **Logic Description**

- **Forward Conveyor Logic:**
  
  - The forward conveyor (forward_conveyor_belt) runs if:
    - The start button is pressed OR
    - The conveyor is already running OR
    - The object counter has reached its preset value
  - It also ensures that the reverse conveyor is OFF and no sensors (object_sensor, defect_sensor, box_sensor) are active.

- **Object Counting:**

  - Uses a counter (object_count) that increments when the object_sensor detects a new item.
  - Resets the count based on reset_count, which is triggered by a detected defect or box placement.
  - The counter's current value is stored in box_count.
  - Preset value of the counter dynamically updates when a defective piece is detected. It becomes initial_count - pieces_not_removed, ensuring that defective items are replaced to maintain the target quantity in the box.
    
- **Defect Handling:**
  
  - If a defect_sensor is triggered:
    - Calculates pieces_not_removed
    - Activates the reverse_conveyor_belt to send the defective piece back
    - Ensures the reverse conveyor only runs when appropriate and avoids conflicts with the forward conveyor or object detection
      
🔧 **Tools Used**

- _**Platform:**_ CODESYS Simulation
- _**Language:**_ Structured Text (ST)

🛠️ **Tools Needed to Simulate**

- CODESYS Control Win SysTray (x64)
- CODESYS Gateway SysTray (x64)

📌 **Notes**

- This project demonstrates counter blocks, conditional state toggling, and multi-sensor-based process logic
- Best suited for those practicing real-world industrial automation logic like sorting and routing on conveyor belts
- Especially useful for understanding how to dynamically modify a counter's preset based on system feedback (e.g., defective products)
- No output is shown, as this is a syntax and logic practice file
- Code is provided in 'conveyor_belt.txt'

