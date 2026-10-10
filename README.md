READ ME

# PMO Portfolio Intelligence - Power BI Dashboard

Power BI dashboard for a portfolio of 15 finance projects. It answers four questions: is anything late or over budget, are people logging time, are projects delivering savings, and can the reported status be trusted.

The data is simulated (dummy data). The styling is inspired by DHL Express, and the scenario is inspired by the kind of finance projects a large express-logistics company might run. It contains no real DHL data and is an independent portfolio project, not affiliated with or endorsed by DHL.

![Overview](screenshots/overview.png)
![Project details](screenshots/project-details.png)

## What is in this repo

- `PMO_Dashboard.pbix` - the Power BI file (open with Power BI Desktop, Windows)
- `PMO_Dashboard_pdf.pdf` - both pages as a PDF
- `PMO_Portfolio_Data_Model.xlsx` - the synthetic data (Projects, Monthly and DateTable)
- `PMO_Portfolio_Dashboard__One-Page_Brief.pdf` - one-page summary: problem, what I built, findings, colour rule, next steps
- `PMO_Governance_Rulebook.pdf` - KPI definitions, colour rules, adoption plan, stakeholders, meetings and access requests

## The data

15 projects across 5 departments, 5 regions and 3 project types. Total budget EUR 3.725M. Projects has one row per project (budget, dates, forecast cost, savings, reported colour). Monthly has 180 rows of planned and actual spend and hours allocated and logged, Oct 2025 to Sep 2026.

## Assumptions

- Data is synthetic. No real company data.
- EUR, as of 30 Sep 2026, monthly data Oct 2025 to Sep 2026.
- RAG rule (common PMO practice, an assumption): Red if forecast cost is over budget by more than 15%, or the end date slips more than 30 days, or forecast savings are more than 25% below plan. Amber at 5%, 8 days, 10%. Green otherwise.
- Cost variance = forecast at completion vs budget.
- Benefits are measured over 12 months from go-live against a pro-rated target.
- Utilization = hours logged / hours allocated. Healthy band 85 to 100%.
- Stale = no update for more than 30 days.
- The Period filter changes hours and utilization only.

## Features

**Overview page:** dropdown filters (Department, Project type, Project manager, Period) with a reset button, three self-writing insight sentences, five KPI cards, click-to-filter status chart, reported vs calculated status check, budget vs forecast vs spend with a switchable breakdown, promised vs forecast savings, and hours allocated vs logged by month.

**Project Details page:** table of all 15 projects with calculated status, cost variance, slip days, days since update, benefit status and the manager's comment.

## Key findings

- 5 of 15 projects report a better status than the numbers show. Only 6 of 15 are Green and 4 are Red.
- Forecast cost is 7.0% over budget and forecast savings are 9.1% below plan.
- Hours logged are 91% of hours allocated, and 2 projects have had no update for over 30 days.
