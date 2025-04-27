# Healthcare Trend Analysis

A full-stack analytics pipeline to scrape, process, store, analyze, and visualize trends in medical research, disease outbreaks, emerging technologies, and healthcare investments.

## Table of Contents

1. [Project Overview](#project-overview)  
2. [What We Did](#what-we-did)  
3. [Skills & Technologies](#skills--technologies)  
4. [Insights Generated](#insights-generated)  
5. [Getting Started](#getting-started)  
6. [Folder Structure](#folder-structure)  
7. [Contributing](#contributing)  
8. [License](#license)  
9. [Contact](#contact)  

---

## Project Overview

We scrape medical research articles and news from sites like **WebMD**, **Healthline**, **Medical News Today**, and **PubMed**, then clean, categorize, and store the data in an SQL database. We apply NLP to extract entities and measure trend velocity, run SQL-based analyses to identify patterns over time and geography, and surface the results in an interactive Power BI dashboard.

---

## What We Did

1. **Data Collection**  
   - Automated web scraping of headlines, summaries, and URLs using `requests`/BeautifulSoup and Selenium.  
   - Parameterized scripts (`--query`, `--max_results`) targeting research topics, treatments, outbreaks, and technologies.

2. **Data Cleaning & Categorization**  
   - Removed duplicates and irrelevant content.  
   - Standardized formats (dates, categories).  
   - Tagged records into topics: treatments, disease outbreaks, technologies, policy, investments.

3. **Data Storage**  
   - Designed a relational schema in MySQL.  
   - Loaded cleaned data via SQLAlchemy and `pandas.to_sql()` for incremental ETL.

4. **Trend Analysis (SQL)**  
   - Wrote parameterized SQL queries and views to compute:  
     - Topic frequency over time  
     - Geographic heatmaps  
     - Correlation between policy events and topic spikes  
   - Calculated “trend velocity” to detect rapid keyword surges.

5. **NLP & Text Analytics**  
   - Used SpaCy for tokenization, lemmatization, and Named Entity Recognition (NER).  
   - Applied `CountVectorizer`/`TfidfVectorizer` to find top terms and compute term importance.  
   - Built co-occurrence matrices and velocity metrics for key entities.

6. **Python ↔ SQL Integration**  
   - Established SQLAlchemy connections for ORM and raw SQL execution.  
   - Modular scripts for data insert, update, and upsert operations.

7. **SQL → Power BI Integration**  
   - Connected Power BI Desktop via DirectQuery/MySQL connector.  
   - Created optimized views in SQL for live dashboards and scheduled refreshes.

8. **Power BI Dashboard**  
   - KPI cards for total articles, top topics, month-over-month growth  
   - Bar & clustered charts for top-N topics by category  
   - Line charts for trend over time  
   - Geographic heat maps for outbreak spread and technology adoption  
   - Word clouds and tables showing entity frequency and co-occurrence  

---

## Skills & Technologies

- **Web Scraping:** `requests`, BeautifulSoup, Selenium, WebDriver-Manager  
- **NLP:** SpaCy, scikit-learn’s CountVectorizer & TfidfVectorizer  
- **Database:** MySQL, SQLAlchemy, raw SQL. 
- **Visualization:** Power BI (DirectQuery, data modeling, custom visuals)  
- **ETL & Analysis:** Python, pandas, NumPy  

---

## Insights Generated

1. **Emerging Treatments & Technologies**  
   – Tracked rise of CRISPR, immunotherapy, robotic surgery via trend velocity.  
2. **Disease Outbreak Patterns**  
   – Mapped geographic spread of COVID-19, Ebola, and malaria with heat maps.  
3. **Healthcare Investment Trends**  
   – Identified biotech and telemedicine funding surges from scraped startup data.  
4. **Emerging Markets**  
   – Highlighted fast-growing healthcare sectors in Asia-Pacific and Africa.  
5. **Policy Correlations**  
   – Correlated insurance reforms and value-based care policies with technology adoption.  
6. **Regional Tech Adoption**  
   – Quantified AI-powered diagnostics and telemedicine uptake by region.  
7. **Future Demand Forecasts**  
   – Predicted geriatric care and home-healthcare needs based on aging-population trends.  
8. **Digital Health Impact**  
   – Measured patient engagement improvements from mobile health apps and wearables.  
9. **Personalized Medicine Trends**  
   – Tracked pharmacogenomics and personalized therapy mentions over time.

---

## Getting Started

1. **Clone the repository**  
   ```bash
   git clone https://github.com/akeesh13/Healthcare-Trend-Analysis.git
   cd Healthcare-Trend-Analysis
   ```

2. **Install dependencies**  
   ```bash
   pip install -r requirements.txt
   ```

3. **Configure your database**  
   - Edit connection string in `config.yaml`.  
   - Run `sql/schema.sql` to create tables and `sql/views.sql` for views.

4. **Run scrapers**  
   ```bash
   python scripts/scrapper.py 

   ```

5. **Clean & load data**  
   ```bash
   python scripts/preprocessing.py
   ```

6. **Launch Power BI Dashboard**  
   - Open `Dashboard/dashboard.pbix` and refresh data.

---

## Folder Structure

    healthcare-trend-analysis/
    ├── data/                     # raw & cleaned CSVs
    ├── scripts/                  # scraping, cleaning, ETL, analysis
    ├── sql/                      # schema & view definitions
    ├── Dashboard/                # Power BI report file
    ├── requirements.txt
    ├── config.yaml               # DB credentials & parameters
    └── README.md

---

## Contributing

1. Fork the repository  
2. Create a feature branch (`git checkout -b feature/XYZ`)  
3. Commit your changes (`git commit -m "Add new feature"`)  
4. Push to your branch (`git push origin feature/XYZ`)  
5. Open a Pull Request

---
