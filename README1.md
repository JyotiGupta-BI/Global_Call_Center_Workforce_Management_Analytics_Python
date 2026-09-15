📊 Global Call Center Workforce Optimization & Stress Testing Analysis

📌 Executive Summary
This project delivers an end-to-end Workforce Optimization (WFO) analysis across **20 global contact center queues** handling multi-channel customer interactions (Voice, Email, Chat) across AMER, EMEA, and APAC regions. 
Using descriptive statistics, capacity modeling, correlation analysis, and scenario stress testing across **10,000 operational records**, this analysis identifies critical staffing bottlenecks, quantifies financial risk exposure under operational shocks, and establishes actionable workforce management strategies.

---

📑 Table of Contents
1. [Project Structure & Methodology](#-project-structure--methodology)
2. [Phase 1: Workload & Descriptive Analysis](#-phase-1-workload--descriptive-analysis)
3. [Phase 2: Capacity & Headcount Planning](#-phase-2-capacity--headcount-planning)
4. [Phase 3: Correlation & Operational Performance](#-phase-3-correlation--operational-performance)
5. [Phase 4: What-If Scenario Stress Testing](#-phase-4-what-if-scenario-stress-testing)
6. [Key Strategic Recommendations](#-key-strategic-recommendations)
7. [Installation & Execution](#-installation--execution)

---

🛠 Project Structure & Methodology

The analysis follows a 4-Phase WFO Framework:
* **Phase 1: Descriptive Analytics** – Evaluates volume trends, Average Handle Time (AHT) distributions, and workload hours ($Workload = \frac{\text{Volume} \times \text{AHT}}{3600}$).
* **Phase 2: Capacity Planning** – Calculates required FTEs based on target occupancy ($85\%$) and net available FTEs post-shrinkage to compute capacity gaps.
* **Phase 3: Operational Correlation** – Analyzes linear dependencies between volume, handle times, shrinkage, and staffing deficits.
* **Phase 4: Stress Testing** – Models operational resilience against shrinkage spikes (+20%) and volume surges (+15% volume, +10% AHT).

---

📈 Key Insights by Analysis Phase

### 🔹 Phase 1: Workload & Descriptive Analysis
* **Top Workload Drivers:** High-tier queues such as `AMER_EMAIL_SUPPORT_T3`, `EMEA_RETAIL_VOICE_T2`, and `EMEA_EMAIL_SUPPORT_T3` generate the highest daily workload hours (~40–45 hours/day per queue unit).
* **AHT Variance:** Handle times demonstrate high variance in complex Tier 3 email and voice support queues (AHT reaching up to 900 seconds), creating scheduling instability.

### 🔹 Phase 2: Capacity & Headcount Planning
* **Systemic Staffing Deficit:** Every single queue in the baseline operational environment runs at a net deficit, with average queue-level deficits ranging between **-2.71 FTE** and **-3.16 FTE**.
* **Highest Deficit Queues:** `EMEA_RETAIL_VOICE_T2` (-3.16 FTE) and `AMER_EMAIL_SUPPORT_T3` (-3.13 FTE) experience the most severe operational understaffing.

### 🔹 Phase 3: Correlation & Operational Performance
* **Workload vs FTE Gap ($r = -0.79$):** Strong negative correlation between total workload hours and FTE gaps, proving that current scheduling models fail to scale proportionally with workload demand.
* **Shrinkage Impact ($r = -0.07$):** Shrinkage acts as a baseline reducer of available agent hours, directly inflating required rostered headcount.

### 🔹 Phase 4: What-If Scenario Stress Testing
* **Baseline Requirement:** **71,266 total aggregate required FTEs** across all operational periods.
* **Scenario 1 (Shrinkage Spike +20%):** Required headcount expands to **85,519 FTEs**, driving daily financial overtime exposure to **$78,413.38/day**.
* **Scenario 2 (Crisis Volume Surge +15% Vol, +10% AHT):** Total workload shock drives daily financial risk to **$118,317.74/day** in overtime exposure.

---

## 💡 Key Strategic Recommendations
1. **Implement Cross-Queue Multi-Skilling:** Establish cross-training programs between Tier 1/2 Chat and Email queues to absorb sudden volume spikes without hiring additional FTEs.
2. **Dynamic Shrinkage Buffering:** Adjust baseline shift scheduling models to include an adaptive 5–10% shrinkage buffer during high-volume regional windows.
3. **Automate Routine Inquiries:** Deploy AI-driven self-service bots for routine Tier 1 Email and Chat queues to reduce AHT by 10–15%.

Key Capabilities Included in This Script
	1. Exact Erlang C Math: Implements probability of wait P(W>0) and exponential delay formulas to compute true queue-level staffing requirements rather than simple averages.
	2. Integrated Financials & WFM: Combines shrinkage, occupancy, workload hours, FTE variance, cost per call, and net revenue margins into a single dataframe.
	3. Parametric & Non-Parametric Statistics: Outputs P50, P90, P95, and IQR across operational variables for resume and portfolio presentation.
	4. Automated Stress Testing: Dynamically simulates how macroeconomic spikes (+15% volume, +5% shrinkage) cascade into Erlang headcount spikes and labor budget overruns.

---

## 🚀 Installation & Execution

# Install required dependencies
pip install pandas numpy matplotlib seaborn openpyxl

# Run full 4-phase analysis script
python wfo_analysis_pipeline.pynb
