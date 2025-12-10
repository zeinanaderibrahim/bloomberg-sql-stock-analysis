Equity Performance Analysis Using Bloomberg Data (SQL + R)
A study into how evolving policy shifts, sector exposures, and company-level dispersion shape current equity market performance.

1. Context & Motivation:
Markets in 2025 continue to react to a complex mix of macroeconomic forces. Among the significant catalysts:

- renewed discussions of broad import tariffs under the new U.S. administration

- supply chain realignments affecting industrials and manufacturing

- shifting expectations around global trade relationships

- sector-specific sensitivities to input costs, labour dynamics, and regulation

Against this macroeconomic backdrop, a natural question emerges:

“Which sectors are positioned to benefit or suffer under tariff-driven market dynamics? And which companies are driving overall dispersion?”

This project builds a workflow designed to answer exactly that kind of question in a clean, structured, and repeatable way.

2. Methodology

1: Data Import & Validation (R)

- Load Bloomberg price and metadata files

- Verify ticker integrity and sector labels

- Prepare the dataset for SQL processing

Script: R/import_data.R

2: Data Cleaning & Structuring (SQL)

- Join prices with company metadata

- Calculate daily returns

- Create sector-level groupings

- Prepare for cross-sectional comparisons

Script: sql/analysis_queries.sql

3: Return Analysis & Sector Comparisons (R)

- Examine cumulative performance

- Compare sector resilience vs tariff sensitivity

- Analyse dispersion within exposed sectors (e.g., industrials, consumer discretionary, tech hardware)

- Identify companies benefiting from reshoring, onshoring, or supply chain localisation themes

Script: R/analysis.R

3. Preliminary Observations

These will update as analysis progresses, but examples of expected insights include:

- Industrials & manufacturing may show divergence depending on import reliance and ability to reprice output

- Consumer goods with high imported input exposure may face margin compression

- Semiconductors and hardware could experience near-term volatility given globalised supply chains

- Energy and materials often behave differently during tariff regimes due to changes in cross-border demand

- Companies with domestic supply chains may outperform peers dependent on foreign components

4. Project Structure

bloomberg-sql-stock-analysis/
│
├── data/
│   ├── prices.csv                 # Bloomberg price data
│   ├── metadata.csv               # Ticker, sector, and company info
│   └── sector_mapping.csv         #  Additional sector classification
│
├── sql/
│   ├── analysis_queries.sql        # Core return and ranking queries
│   ├── cleaning_queries.sql        # Data preparation and standardisation
│   └── sector_performance.sql      # Sector-level aggregation and comparisons
│
├── R/
│   ├── import_data.R               # Load and validate raw Bloomberg exports
│   ├── analysis.R                  # Core return analysis and dispersion work
│   ├── clean_data.R                # Additional preprocessing logic
│   └── sector_returns.R            # Sector-level decomposition and visuals
│
└── reports/
    └── bloomberg_analysis.Rmd      # Narrative-style analysis and charts
