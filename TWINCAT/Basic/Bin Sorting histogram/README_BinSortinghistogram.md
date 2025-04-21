📊 **Histogram Binning Logic**

This program classifies an array of ten input values into three histogram bins: negative values, zero, and positive values (0 to 10). The result is displayed on an HMI as a basic bar chart with three bars.

🧩 **Logic Description**

- A FOR loop iterates over 10 input[i] values.
- Each value is categorized into one of three bins:
  - bins[0]: For negative values
  - bins[1]: For zeros
  - bins[2]: For positive values (0 < x ≤ 10)
- After every full cycle (cycle_counter > 10), the bin counts are reset to allow continuous monitoring of new input sets.

📈 **Trend Observation**

- _Fluctuating Bars:_ The HMI reflects the changing distribution of values with every cycle, so the height of each bar adjusts based on real-time input trends.
- _Basic Categorization Insight:_ Useful for quickly spotting whether the system is receiving more negative, neutral, or positive readings over time.

💻 **HMI Overview**

- A 3-bar histogram represents the bins.
- TwinCAT HMI displays each bar dynamically based on bin counts.
⚠️ While TwinCAT’s native HMI is limited, it still supports simple real-time visualizations like bar graphs. For more advanced or animated charts, integration with third-party platforms or custom visuals would enhance user experience.

🔧 **Tools Used**

_**Platform:**_ Beckhoff TwinCAT 3.1

_**Language:**_ Structured Text (ST)

🛠️ **Tools Needed to Simulate**

- TwinCAT XAE (Extended Automation Engineering) environment
- Weekly runtime license (valid for 7 days, can be renewed)
  
📌 **Notes**

- Code is provided in 'histogram bin sorting st.txt'.
- Easy-to-understand example for data classification in automation.
- Can be extended to more bins for detailed histograms.
- Potential upgrade: Real-time graph animation or extended bin ranges using enhanced HMI features.
