
# Vendor Performance Analytics

An end-to-end data analytics project focused on evaluating vendor performance, procurement efficiency, inventory management, purchasing patterns, and profitability using SQL, Python, and Power BI.

## 📌 Project Overview

Effective vendor management plays a crucial role in optimising procurement costs, maintaining healthy inventory levels, and improving business profitability.

This project analyses vendor and inventory-related data to identify high-performing vendors, evaluate purchasing patterns, investigate inventory turnover, and uncover opportunities for cost optimisation.

The analysis combines SQL-based data preparation, Python-driven exploratory data analysis and statistical analysis, and an interactive Power BI dashboard to generate actionable business insights.

## 🎯 Business Objectives

The primary objectives of this project are:

- Evaluate vendor and brand performance based on sales and profitability.
- Identify vendors contributing the most to total procurement expenditure.
- Analyse the relationship between purchase quantities, sales quantities, and inventory turnover.
- Investigate the impact of bulk purchasing on unit purchase prices.
- Identify slow-moving inventory and excess stock.
- Understand the capital tied up in unsold inventory.
- Compare profit margins between high-performing and low-performing vendors.
- Identify opportunities for pricing adjustments, promotional strategies, and procurement optimisation.

## 🛠️ Technology Stack

| Technology | Application |
|---|---|
| SQL | Data extraction, querying, aggregation, and database analysis |
| Python | Exploratory data analysis and statistical analysis |
| Pandas & NumPy | Data manipulation and numerical computations |
| Matplotlib & Seaborn | Data visualisation |
| SciPy | Statistical testing and confidence intervals |
| SQLite | Database management |
| Power BI | Interactive dashboard and business reporting |
| Jupyter Notebook | Analysis and documentation |

## 📂 Project Structure

```text
Analytics_project/
│
├── Dashboard/
│   └── Analytics_Project.pbix
│
├── Data/
│   ├── begin_inventory.csv
│   ├── end_inventory.csv
│   ├── purchase_prices.csv
│   └── vendor_invoice.csv
│
├── Notebooks/
│   └── Vendor_Performance_analysis_analytics_project.ipynb
│
├── README.md
├── .gitignore
└── LICENSE
```

**Note:** Large raw datasets (`sales.csv` and `purchases.csv`) and the SQLite database (`inventory.db`) are excluded from this repository because of their file sizes. They need to be obtained or recreated locally before running the complete analysis.

## 🔍 Project Workflow

### 1. Data Preparation and SQL Analysis

The project uses SQLite to store and analyse the underlying vendor, sales, purchase, and inventory information.

A consolidated table named `vendor_sales_summary` is used as the primary source for the Python analysis.

The analysis works with measures including:

- Vendor and brand information
- Purchase price and actual price
- Total purchase quantity
- Total sales quantity
- Total purchase and sales dollars
- Gross profit and profit margin
- Freight cost
- Stock turnover

### 2. Exploratory Data Analysis (EDA)

Python was used to understand the distribution, variability, and relationships between important business variables.

Key techniques included:

- Descriptive statistics
- Histograms and distribution plots
- Boxplots for outlier detection
- Categorical count plots
- Correlation heatmaps
- Filtering inconsistent observations

The analysis also examined negative and zero values in gross profit, profit margin, and sales quantities.

### 3. Business Analysis

The project investigates several business questions.

#### A. Identifying Brands Requiring Promotional or Pricing Adjustments

Identified brands with relatively low sales performance but higher profit margins to explore opportunities for improving sales through promotional and pricing strategies.

#### B. Identifying Top-Performing Vendors and Brands

Compared vendors and brands based on total sales dollars to identify the strongest contributors to business performance.

#### C. Vendor Contribution to Procurement Expenditure

Analysed vendor purchase contributions using percentage contribution and cumulative contribution. A Pareto-style analysis was used to understand procurement concentration among the leading vendors.

#### D. Impact of Bulk Purchasing on Unit Prices

Compared unit purchase prices across different order-size categories to investigate whether larger purchase quantities are associated with lower unit costs.

The notebook reports that large orders had the lowest average unit purchase price, approximately $10.78, with a substantial difference compared with smaller orders.

#### E. Inventory Turnover and Excess Stock

Investigated vendors with low inventory turnover to identify potential slow-moving inventory and inventory management inefficiencies.

#### F. Capital Locked in Unsold Inventory

Examined the value of unsold inventory across vendors to identify where working capital may be tied up in excess stock.

### 4. Statistical Analysis

Statistical techniques were used to compare the profitability of high-performing and low-performing vendors.

#### 95% Confidence Interval Analysis

Calculated 95% confidence intervals for the profit margins of top-performing and low-performing vendors.

| Vendor Category | 95% Confidence Interval |
|---|---|
| Top-performing vendors | 30.74% – 31.61% |
| Low-performing vendors | 40.50% – 42.64% |

The results indicate higher profit margins among low-performing vendors, suggesting potential differences in pricing, product mix, or cost structures.

#### Hypothesis Testing – Two-Sample T-Test

The following hypotheses were formulated:

- **Null Hypothesis (H₀):** There is no significant difference in the mean profit margins of top-performing and low-performing vendors.
- **Alternative Hypothesis (H₁):** There is a significant difference in the mean profit margins of top-performing and low-performing vendors.

A two-sample independent t-test (Welch's t-test) was performed using SciPy, with a significance level of 0.05.

## 📊 Power BI Dashboard

The project includes a Power BI dashboard designed to present vendor performance and procurement-related metrics in an accessible visual format.

**Dashboard file:** `Dashboard/Analytics_Project.pbix`

Open the file using Microsoft Power BI Desktop.

## 💡 Key Business Insights

The analysis produced several observations:

1. **Vendor and brand performance:** Sales performance varies across vendors and brands, making vendor-level and brand-level evaluation important for identifying business opportunities.

2. **Procurement concentration:** Purchase contribution and cumulative contribution analysis help identify the extent to which procurement expenditure depends on leading vendors.

3. **Bulk purchasing:** Larger order sizes were associated with lower unit purchase prices in the analysed data, highlighting potential procurement cost-saving opportunities.

4. **Inventory management:** Low inventory turnover can indicate slow-moving stock and possible inefficiencies in inventory allocation.

5. **Profitability differences:** Low-performing vendors demonstrated higher profit margins than top-performing vendors in the notebook's confidence interval analysis.

6. **Pricing and promotional opportunities:** Brands with relatively low sales but higher profit margins may offer opportunities for targeted promotions and pricing adjustments.

## ⚙️ Installation and Setup

### Prerequisites

- Python 3.x
- Jupyter Notebook
- SQLite
- Microsoft Power BI Desktop

### Python Libraries

Install the required libraries:

```bash
pip install pandas numpy matplotlib seaborn scipy jupyter
```

### Database Setup

The notebook connects to a SQLite database named `inventory.db` and retrieves data from a table called `vendor_sales_summary`.

The database is not included in this repository because of its size.

To reproduce the analysis:

1. Obtain the original project datasets from the source mentioned below.
2. Set up the SQLite database locally.
3. Recreate the required tables and `vendor_sales_summary` using the original SQL workflow.
4. Place `inventory.db` in the appropriate working directory or update the notebook's database path.

### Running the Notebook

Navigate to the project directory and launch Jupyter Notebook:

```bash
jupyter notebook
```

Open:

```text
Notebooks/Vendor_Performance_analysis_analytics_project.ipynb
```

Ensure that the database and required summary table are available before executing the notebook.

### Opening the Power BI Dashboard

1. Install Microsoft Power BI Desktop.
2. Open `Dashboard/Analytics_Project.pbix`.
3. If prompted, configure the local data source paths and refresh the data.

## 📁 Dataset and Learning Resources

This project was developed by following the tutorial:

**Vendor Performance Data Analytics End-To-End Project | SQL + Python + Power BI + Reporting**

[Watch the original YouTube tutorial](https://youtu.be/nmCfNHjfgEY?si=0GkIsJB8alJPHKsc)

**Original dataset resource:**

[Access the dataset download page](https://topmate.io/ayushi_mishra/1557424)

Credit and acknowledgement go to the original tutorial creator for the learning resource and project guidance.

## 🚀 Future Improvements

Potential extensions to this project include:

- Automating the vendor performance reporting pipeline.
- Developing vendor performance scorecards.
- Adding predictive models for inventory demand forecasting.
- Implementing automated alerts for slow-moving inventory.
- Building vendor risk and dependency indicators.
- Enhancing the Power BI dashboard with additional drill-down analysis.

## 👩‍💻 Author

**Mugdha Chaturvedi**

GitHub: [mugdhaaa15-pixel](https://github.com/mugdhaaa15-pixel)

---

*This project was completed as a hands-on learning project in SQL, Python, data analytics, statistical analysis, and Power BI, following the referenced tutorial.*
