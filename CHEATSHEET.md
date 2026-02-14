# 📊 Cheatsheet 1: Smart Meter Energy Analytics
**File:** `energy-usage-analysis/CHEATSHEET.md`

### 1. The Variables
| Variable | Professional Name | What it represents |
| :--- | :--- | :--- |
| **`LCLid`** | Unique Identifier | Represents one specific household meter. |
| **`Energy_kWh`** | **Response Variable** | Energy used in a 30-min window (The "Target"). |
| **`HH_Numeric`** | Temporal Feature | Time of day converted to 0–47 slots. |
| **`Rolling_Mean`** | **Dynamic Baseline** | The "typical" usage for that specific house over 24h. |
| **`3-Sigma`** | Anomaly Threshold | Statistical limit: Mean + (3 * Standard Deviation). |

### 2. The Logic & The "Why"
*   **Data Reshaping (Melt):** We moved from "Wide" to "Long" format. *Why?* Because Machine Learning models require each observation to be its own row (**Tidy Data**).
*   **Window Functions (SQL):** We used `RANK() OVER (PARTITION BY LCLid...)`. *Why?* This allows us to compare a household’s peaks against itself, rather than comparing a mansion to a small flat.
*   **Prophet Forecasting:** It handles **Seasonality** (Winter vs. Summer) automatically. *Why?* Grid operators need to know demand 7 days in advance to manage supply costs.

### 3. Interview Script
> "I processed 1.2M rows of UK energy data. I used a **Rolling 3-Sigma threshold** to build an automated alert system. This identifies 'Actionable Alerts' where usage is statistically impossible for that specific user, which is key for detecting faulty meters or fraud."
