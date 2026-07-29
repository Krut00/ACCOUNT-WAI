# Screener.in Dashboard Project: Rebuild Plan and Report

## Part 1: Project Rebuild Plan

### 1. Project goal
- Build a Streamlit dashboard that uses live Screener.in data only.
- Show key accounting metrics for a selected company.
- Include revenue, growth, operating profit, OPM, EBITDA, EPS, cash flows, working capital, margins, equity capital, dividend payout, and investment guidance.
- Add clear reasons and risks to support investment judgement.
- Make the app deployment-ready for Streamlit Community Cloud.

### 2. Repository setup
- Create a new GitHub repository.
- Add the following files:
  - `accounting_dashboard_streamlit.py`
  - `requirements.txt`
  - `runtime.txt`
  - `README.md`
  - `.gitignore`
  - `.streamlit/secrets.toml` (optional example)

### 3. Dependencies
- `streamlit`
- `pandas`
- `requests`

Optional:
- `beautifulsoup4` for more robust HTML parsing.

### 4. Data layer architecture
- Scrape live data from Screener.in consolidated pages for the selected company.
- Parse row labels and numeric values from the page.
- Automatically select the newest available year or quarter column.
- Extract and normalize accounting metrics into a clean data structure.

### 5. Metrics to include
- Revenue / Sales
- Prior-year Revenue for growth comparison
- COGS / Expenses
- Operating Profit
- EBITDA
- Earnings per Share (EPS)
- Cash Flow from Operations (CFO)
- Cash Flow from Investing (CFI)
- Cash Flow from Financing (CFF)
- Inventory Days
- Receivable Days
- Equity Capital
- Dividend Payout %

### 6. User interface design
- Sidebar controls for ticker input, search suggestions, refresh, and data source toggles.
- Main page sections for key metrics, cash flow, summary, and investment guidance.
- Clean visual layout with cards, tables, and clearly labeled sections.

### 7. Live-only behavior
- Use live Screener data when available.
- If live data is unavailable, show a clear notification.
- Do not silently fall back to dummy or sample values.
- Allow manual overrides only if explicitly enabled.

### 8. Robustness and error handling
- Parse numbers safely and support currency, commas, and percentages.
- Guard arithmetic calculations against missing or null values.
- Use safe chart fallbacks to avoid runtime issues.
- Display helpful error messages when scraping fails.

### 9. Local testing
- Run `python3 -m py_compile accounting_dashboard_streamlit.py`.
- Run `streamlit run accounting_dashboard_streamlit.py`.
- Validate with multiple tickers and verify the latest year values.
- Check behavior when the Screener page is unavailable.

### 10. Deployment preparation
- Add a supported Python version in `runtime.txt`.
- Pin dependencies in `requirements.txt`.
- Document deployment instructions in `README.md`.

### 11. Deployment steps
- Push the repository to GitHub.
- Create a new app on Streamlit Community Cloud.
- Choose the main file: `accounting_dashboard_streamlit.py`.
- Deploy and verify the live application.

### 12. Optional enhancements
- Add caching for Scraper results.
- Add more KPIs like ROE, debt-to-equity, and net margin.
- Add company profile or valuation context.
- Add better visuals with safe Streamlit charts.
- Add automatic layout-change detection for Screener pages.

## Part 2: Professor-Ready Report

### Project description
This project is a financial dashboard built in Streamlit that pulls live accounting and cash-flow data from Screener.in for publicly listed Indian companies. The dashboard uses the latest available financial period from Screener and calculates core performance metrics, cash-flow measures, working capital ratios, and investment guidance.

### Included features and their purpose

#### Live Screener data scraping
- The app retrieves real-time company financials from Screener.in.
- This ensures the dashboard reflects the most recent reported performance rather than stale sample data.
- Using live data improves the reliability of investment screening.

#### Revenue and growth
- Revenue is shown for the latest period, along with prior-year revenue.
- Growth is calculated as the change in revenue versus the previous period.
- Revenue growth indicates whether the company is expanding its top line and can signal healthy demand and market traction.

#### Operating Profit and OPM
- Operating Profit is the profit earned from core business activities.
- Operating Profit Margin (OPM) is the ratio of operating profit to revenue.
- High OPM indicates the company is efficiently converting sales into operating profit, which helps assess operational strength.

#### EBITDA
- EBITDA approximates cash earnings before interest, taxes, depreciation, and amortization.
- It helps compare operating performance across companies with different capital structures and tax situations.

#### EPS (Earnings per Share)
- EPS measures the earnings allocated to each outstanding share.
- A stable or growing EPS shows that shareholders are receiving increasing value from the company’s net profit.

#### Cash flow metrics: CFO, CFI, CFF
- Cash Flow from Operations (CFO) shows whether the company generates cash from its core business.
- Cash Flow from Investing (CFI) reveals investment spending on assets, acquisitions, and capital expenditures.
- Cash Flow from Financing (CFF) shows capital raising, debt repayments, and dividend flow.
- Together, these cash-flow items show whether reported profits are translating into real cash and whether the company is reinvesting or returning profits to owners.

#### Working capital metrics: Inventory and Receivable Days
- Inventory Days estimate how long inventory is held before sale.
- Receivable Days estimate how long customers take to pay.
- Efficient working capital management means less cash is tied up in operations, which supports liquidity and reduces financing risk.

#### Gross margin
- Gross margin shows the percentage of revenue remaining after direct costs.
- It indicates pricing power and cost control in the company’s core operations.

#### Equity capital and dividend payout
- Equity capital provides a sense of the shareholder base and capital structure.
- Dividend payout percentage indicates how much profit is returned to shareholders versus retained for growth.
- Together, these metrics help evaluate capital allocation and shareholder return policy.

#### Investment guidance and scoring
- The dashboard generates a simple signal based on key thresholds:
  - Revenue growth target
  - Operating profit margin target
  - Gross profit margin target
  - Positive operating cash flow
  - Efficient receivable days
- This helps users quickly assess whether a company is likely operating with healthy fundamentals.

### Why these features matter for investment analysis
- Real-time data ensures the analysis is based on the latest financial period, which is critical for fast-moving markets.
- Revenue growth and margins show whether the business is expanding profitably.
- Cash-flow measures validate whether earnings are supported by actual cash generation.
- Working capital metrics identify how efficiently the company manages short-term assets and liabilities.
- Dividend payout and equity capital provide context on shareholder returns and capital stability.
- Combining these metrics yields a more complete view than looking at a single ratio alone.

### Summary of project value
This dashboard is designed to help an accounting student or investor understand whether a listed company is financially sound and investable. It combines income statement performance, cash-flow quality, working capital efficiency, and shareholder return indicators into a single analytic tool. The result is a practical, live-data-supported framework for quick fundamental screening and follow-up research.
