# Task-05_Descriptive-Stats
Syracuse University Women’s Lacrosse 2023-2024 — Performance Analysis vs LLMs
This repository analyzes the performance of the Syracuse University Women’s Lacrosse Team during the 2024 season and compares it with the 2023 season to identify trends and player improvements. In parallel, I evaluated how Large Language Models (LLMs) like ChatGPT or Claude perform when answering questions without access to historical data, versus a Python-based analysis pipeline that uses both seasons' data.

## Files in This Repository
- `Task 5_Womens_Lacross_comparison_and_analysis_Apoorva Mahajan.ipynb` — Python analysis script
- `Task 05 Syracuse University Women’s Lacrosse 2024 Statistical Analysis vs LLM Inference.pdf` — Report on findings & visualizations
- `README.md`

## Files used for analysis. Please contact amahaj05@syr.edu for the datasets.
- `2023 SU Womens Lacrosse Cumulative Statistics.xlsx`  
- `2024 SU Womens Lacrosse Cumulative Statistics.xlsx`  
- `team_stats_comparison.csv` — Year-over-year team metrics
- `player_improvement.csv` — Player-level point changes
---

## Objectives

1. Identify top performers in 2024
2. Determine the most improved player from 2023 to 2024
3. Quantify trends in team performance year-over-year
4. Compare answers from a Python script with responses from an LLM
5. Evaluate how LLMs hallucinate or misinterpret data when context is missing

---

## Methodology

### Python-Based Analysis
- Cleaned and standardized player names
- Converted all stat fields to numeric using `.loc` to avoid copy warnings
- Merged 2023 and 2024 data to compute player improvements
- Calculated and compared team-wide averages per game
- Exported all results to CSV for transparency

### LLM Test Prompts
I asked:
> "Summarize the 2024 Syracuse Women’s Lacrosse season: Who was the most improved player, who led in scoring, what trends are visible, and how would you describe the team's play style?"

LLMs had **only the 2024 file**, no access to 2023.

---

## Findings Summary

### Top Scorers (2024)
| Player          | Goals | Assists | Points |
|----------------|-------|---------|--------|
| Emma Tyrrell   | 61    | 31      | **92** |
| Olivia Adamson | 52    | 31      | 83     |
| Natalie Smith  | 47    | 7       | 54     |

---

### Most Improved (2023 → 2024)
| Player         | Points 2023 | Points 2024 | Change |
|----------------|-------------|-------------|--------|
| Payton Rowley | 2           | 38          | **+36** |
| Olivia Adamson| 51          | 83          | +32     |
| Natalie Smith | 29          | 54          | +25     |

✅ **Python Correctly Identifies**: Payton Rowley  
❌ **LLM Mistakenly Picks**: Emma Tyrrell or Olivia Adamson

---

### Team Performance Trends
| Metric             | 2023 Avg | 2024 Avg | Trend               |
|--------------------|----------|----------|----------------------|
| Goals/Game         | 24.31    | 24.53    | ⬆ Slight increase   |
| Assists/Game       | 13.78    | 11.33    | ⬇ Declined          |
| Shots/Game         | 52.3     | 55.1     | ⬆ More attempts     |
| Shooting %         | 29.6%    | 20.6%    | ❌ Efficiency drop  |
| Turnovers/Game     | 22.75    | 26.58    | ⬆ Sloppier play     |
| Ground Balls/Game  | 26.3     | 27.9     | ⬆ Hustle improved   |
| Fouls/Game         | 43.3     | 27.8     | ⬇ Less physicality  |

---

## LLM Limitations

LLMs tend to:
- **Overrate top scorers as “most improved”**
- **Assume improvements** even when efficiency dropped
- **Invent play styles** without numeric support
- **Lack awareness** of multi-season context

> They’re great at *describing*, but not *analyzing* when historical data is missing.

---

## Why Python Was More Accurate

| Feature              | Python Script | LLM Model |
|----------------------|---------------|-----------|
| Uses 2-year data      | ✅ Yes        | ❌ No      |
| Precise player stats  | ✅ Yes        | ❌ Approximate |
| Trend analysis        | ✅ Computed   | ❌ Assumed |
| Repeatability         | ✅ Reproducible | ❌ Prompt-based |
| Transparency          | ✅ Exported CSV | ❌ Black-box answers |

---

## Conclusion

LLMs are useful tools for **language summaries**, but not replacements for structured analysis. By combining raw data, Python, and human insight, we get **more accurate**, **verifiable**, and **nuanced** evaluations.

---

## Sample Prompts for LLM Testing

You can try these questions with Claude, Gemini, or ChatGPT using only the 2024 file:

1. Who were the top scorers for Syracuse Women’s Lacrosse in 2024?
2. Who was the most improved player?
3. What trends are visible in the team’s performance?
4. How would you describe their play style?
5. Can you identify areas of weakness or improvement?

Then compare answers to my Python results. For dataset, please contact me at amahaj05@syr.edu.

---

## License

MIT License.  
All data used from publicly available NCAA sources and Syracuse Athletics.

---

## Acknowledgments

- Syracuse University Athletics Department  
- Pandas, Matplotlib for data visualization  
- ChatGPT, Claude for LLM experimentation
