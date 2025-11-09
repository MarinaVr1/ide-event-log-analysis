# ide-event-log-analysis
Statistical analysis of IDE event logs to investigate behavioral differences between manually and automatically triggered tool windows

**Author:** Marina Vračarić  
**Date:** November 8, 2025  

---

## Project Overview
This project analyzes **tool window usage behavior in Integrated Development Environments (IDEs)** — exploring how long tool windows remain open depending on whether they were triggered *manually* by the user or *automatically* by system events (e.g., during debugging).

The goal is to uncover differences in usage duration patterns, interpret them in the context of user interaction, and evaluate the robustness of findings across multiple data-cleaning strategies.

**Full Report (PDF):** [Download here](https://github.com/MarinaVr1/ide-event-log-analysis/blob/main/projectDescription.pdf)  


## Conclusion

The results strongly suggest that:
> **Manual openings correspond to brief, intentional user interactions**,  
> while **automatic openings capture extended, system-driven processes.**

These findings are consistent across all data-cleaning strategies, reinforcing confidence in the observed behavioral distinction.


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




