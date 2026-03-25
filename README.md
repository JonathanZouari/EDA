# Nexus Digital — Lead Pipeline Deep Dive

## Comprehensive Analysis of FY2024 Lead Data

**Context:**  
Nexus Digital doubled their marketing budget to $3.2M and expanded the sales team from 4 to 6 reps. Lead volume surged 60%, but win rate dropped from 14% to 8.3%. The CEO wants to know: *"Are we generating the wrong leads, or are we failing to convert the right ones?"*

This notebook answers 10 key analytical questions, defines KPIs, and provides actionable recommendations based on sales pipeline data.

---

### Table of Contents

1. [KPI Framework](#kpi-framework)
2. [Q1: Sales Rep Performance](#q1-sales-rep-performance)
3. [Q2: Channel Performance](#q2-channel-performance)
4. [Q3: Funnel Analysis](#q3-funnel-analysis)
5. [Q4: Lead Scoring Impact](#q4-lead-scoring-impact)
6. [Q5: Speed to First Contact](#q5-speed-to-first-contact)
7. [Q6: Lead Qualification Breakdown](#q6-lead-qualification-breakdown)
8. [Q7: Lost Reason Analysis](#q7-lost-reason-analysis)
9. [Q8: Cycle Time Analysis](#q8-cycle-time-analysis)
10. [Q9: High-Performing Segments](#q9-high-performing-segments)
11. [Q10: Recommendations & Action Plan](#q10-recommendations--action-plan)

---

## KPI Framework

| KPI                            | Formula                             | Current Value | Target (Next Q) | Rationale                                                                                   | Owner   |
|---------------------------------|-------------------------------------|--------------|-----------------|---------------------------------------------------------------------------------------------|---------|
| 1. Overall Lead-to-Win Rate    | Won / Total Leads x 100             | 8.3%         | 12%             | Headline metric for CEO. Dropped from 14%. Must improve through targeting and fast response. | RevOps  |
| 2. Closed-Deal Win Rate        | Won / (Won + Lost) x 100            | 20.1%        | 35%             | Sales effectiveness for closed deals.                                                        | Sales   |
| 3. Speed to First Contact (Avg)| AVG(days_to_first_contact), hours   | 20.1h        | <12h            | Strong win correlation with fast response. <12h is key.                                      | Sales   |
| 4. Median Response Hours       | MEDIAN(days_to_first_contact)       | 15.5h        | <10h            | Median resists outliers. Better for SLA.                                                     | Sales   |
| 5. Avg Deal Value (Won)        | AVG(deal_value, status="Won")       | $46,871      | >$55,000        | Key to pipeline health. Reflects deal quality.                                               | Sales   |
| 6. Revenue Per Lead            | SUM(deal_value, Won) / Total Leads  | $3,897       | $5,400          | Blends volume and efficiency.                                                                | RevOps  |
| 7. Avg. Lead Score             | AVG(lead_score)                     | 51.3         | >55             | Are we attracting higher-quality leads?                                                      | Marketing|
| 8. Qualified Rate              | Qualified+ / Total Leads x 100      | 62.0%        | >70%            | % reaching qualification. Reflects lead quality/prep.                                        | SDRs    |
| 9. Avg. Cycle (Won+Lost)       | AVG(cycle_days, status in [Won,Lost])| 37.4 days    | <30d            | Shorter = more velocity, faster revenue.                                                     | Sales   |
|10. "No Response" Lost Rate     | No Response / Lost x 100            | 29.4%        | <18%            | Proxy for follow-up/speed issues.                                                            | SDRs    |

> **Note:** `days_to_first_contact` is measured in **hours**, not days.

---

## Sample Insights

### Q1: Sales Rep Performance

*How are reps performing on lead conversion, speed, and deal value?*

- Pipeline and win rates by rep, including won, lost, pipeline open, and avg. deal value.
- **Visual:** Horizontal bar chart of reps by win rate; color-coded by win/loss.

### Q2: Channel Performance

*Which lead sources contribute most? Which convert best? Underperforming channels?*

- Table showing channel by total leads, win/loss count, win rates, average deal value, and lead score.
- **Visual:** Grouped bar plots for volume and win rate.

### Q3–Q10: Additional Questions

- Funnel drop-off, lead scoring, time-to-first-touch, qualification, lost reasons, cycle times, segmentation, and actionable recommendations.

---

## Usage

Open `lead_pipeline_analysis.ipynb` and follow the sequential analysis. Each cell is annotated, outputs are formatted, and visualizations are included. You will need Python (>=3.8), pandas, numpy, matplotlib, seaborn.

```bash
pip install pandas numpy matplotlib seaborn
```

---

## Executive Summary

Nexus Digital's growth spurt exposed bottlenecks in lead quality and follow-up speed. Conversion dropped even as the team scaled, due to slower response times and channel mix. Key wins are attainable by:
- Responding to leads faster (<12h avg).
- Focusing efforts on higher-scoring channels and segments.
- Reducing "No Response" losts through better process/SLA adherence.
- Tightening qualification criteria and feedback loops between marketing and sales.

**See the notebook for full details, data, and specific action items.**