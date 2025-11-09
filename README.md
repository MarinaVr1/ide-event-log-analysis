# ide-event-log-analysis
Statistical analysis of IDE event logs to investigate behavioral differences between manually and automatically triggered tool windows

**Author:** Marina Vračarić  
**Date:** November 8, 2025  

---

## Project Overview
This project analyzes **tool window usage behavior in Integrated Development Environments (IDEs)** — exploring how long tool windows remain open depending on whether they were triggered *manually* by the user or *automatically* by system events (e.g., during debugging).

The goal is to uncover differences in usage duration patterns, interpret them in the context of user interaction, and evaluate the robustness of findings across multiple data-cleaning strategies.

**Full Report (PDF):** [Download here](./Tool_Window_Usage_Analysis_Report.pdf)  
**Notebook:** [`toolwindowUsageData.ipynb`](./toolwindowUsageData.ipynb)

---

## Data & Methodology

**Dataset:**
- Event logs with anonymized user IDs, timestamps, event types (`open`, `close`), and opening mode (`manual`, `auto`).
- Data preprocessing involved cleaning duplicate or unmatched event pairs and removing outliers above the 95th percentile.

**Data Cleaning Strategies Tested:**
1. **Strategy 1:** Keep the first “open” event in a sequence  
2. **Strategy 1 (95th percentile):** Apply Strategy 1 with high-duration filtering  
3. **Strategy 2:** Keep the last “open” event in a sequence  

---

## Analysis Summary

| Strategy | Median Duration | Mean Duration | Std. Dev. | Observation |
|-----------|----------------|----------------|------------|--------------|
| Strategy 1 | ~12s | ~418s | High | Affected by long outliers |
| Strategy 1 (95th pct) | ~13s | ~844s | Moderate | Outliers reduced |
| Strategy 2 | ~11s | ~360s | Low | Conservative estimate |

**Key Finding:**  
Median and 75th percentile durations are stable across all cleaning strategies, confirming that user behavior patterns are **robust to preprocessing variations**.

---

## Statistical Results

The **Mann–Whitney U test** confirmed significant differences between *manual* and *automatic* openings across all strategies:

| Strategy | p-value | Significance |
|-----------|----------|--------------|
| Strategy 1 | 2.7 × 10⁻⁵³ | Significant |
| Strategy 1 (95th pct) | 4.9 × 10⁻⁵⁵ | Significant |
| Strategy 2 | 4.3 × 10⁻⁵⁹ | Significant |

Interpretation:  
Manually opened tool windows are significantly shorter-lived, representing **focused user actions**, while automatically opened ones correspond to **longer-running background or debugging processes**.

---

## Visualization Highlights

- **Histograms** of duration distributions clearly show right-skewed patterns.  
- Manual events peak at short durations (under ~200s).  
- Automatic events have heavier tails, indicating extended usage.  
- Visual consistency across strategies supports the robustness of the results.

---

## Conclusion

Taken together, the results strongly suggest that:
> **Manual openings correspond to brief, intentional user interactions**,  
> while **automatic openings capture extended, system-driven processes.**

These findings are consistent across all data-cleaning strategies, reinforcing confidence in the observed behavioral distinction.

---

## Tools & Libraries

- **Python 3.10**
- **Pandas** — data manipulation  
- **Matplotlib / Seaborn** — visualization  
- **SciPy** — statistical testing  
- **Jupyter Notebook** — experimentation & analysis  

---

## How to Run

To run this project locally:

1. Download or clone this repository.  
2. Make sure you have **Python** and **Jupyter Notebook** installed.  
3. Install the required libraries
4. Open the notebook file
5. Run all cells to reproduce the analysis and results.




