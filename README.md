# Customer Support Analytics Dashboard

Analyses support-ticket response and resolution times, finds the busiest days and hours, and turns the findings into staffing recommendations. SQL does the metrics; the output feeds an interactive Tableau dashboard.

> **Dataset:** synthetic (8,000 tickets over 8 weeks, fixed random seed), generated inside the notebook so the project is reproducible and uses no confidential data.

## Business questions
1. How quickly does the team send a first response and resolve tickets?
2. On which days and hours does ticket volume peak?
3. Does response time suffer when volume is high? Which channels and categories are slowest?

## Tools
SQL (SQLite) | Python (Pandas, Matplotlib) | Tableau

## Key results (from this dataset)
- 8,000 tickets; average first response **39.7 minutes**; average resolution **14.5 hours**.
- Peak hours: **11:00, 10:00, 14:00**. Busiest day: **Mon**; quietest: **Sun**. **87.1%** of tickets arrive Monday to Friday.
- First responses are slowest in the busiest hours (**10:00, 11:00, 14:00**), so response time rises with volume.
- Slowest channel for first response: **Email**. Slowest category to resolve: **Delivery**.

## Recommendations
- Schedule more agents at the peak hours and on Monday instead of flat staffing.
- Move Email and web-form queries to faster triage during busy hours, or promote Chat and Phone, which respond much faster.
- Review the Delivery process, which has the longest resolution time.

## Project structure
```
02-customer-support-analytics-dashboard/
|-- support_analytics.ipynb         # full analysis (SQL + Python)
|-- data/support_tickets.csv        # generated ticket data
|-- output/
|   |-- tableau_support_tickets.csv # data source for Tableau
|   `-- volume_by_hour.csv
`-- screenshots/                    # add your Tableau dashboard screenshot here
```

## How to run
```bash
pip install -r ../requirements.txt
jupyter notebook support_analytics.ipynb
```

## Tableau dashboard
Build instructions are at the end of the notebook. After publishing, add your Tableau Public link and a screenshot here:

`![Dashboard](screenshots/dashboard.png)`

## Skills demonstrated
SQL (strftime, date arithmetic, GROUP BY) | Time-series and peak analysis | Data visualization | Turning findings into recommendations | Tableau data preparation
