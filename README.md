# Amazon Sales Analysis

A multi-phase data science project that takes ~42,700 scraped Amazon product listings from raw data all the way to statistical modeling, machine learning, and a final set of insights — covering what separates a Best Seller from a regular product, and how sponsorship, price, and rating relate to review volume.

## Project Overview

The project follows a full analytics pipeline, with each phase living in its own folder:

| Phase | Folder | What happens |
|---|---|---|
| 1. Data Cleaning | `Datasets and cleaning/` | Raw scraped listings are parsed and cleaned (prices, ratings, review counts, badges, timestamps) into an analysis-ready CSV |
| 2. Exploratory Data Analysis | `Exploratory Data Analysis/` | Distributions, correlations, Best Seller vs. Regular comparisons, time-series trends, and hypothesis testing |
| 3. Statistical Modeling | `_Statistical Modeling/` | OLS regression explaining review volume from price, rating, sponsorship, and Best Seller status, with multicollinearity (VIF) and residual diagnostics |
| 4. Machine Learning | `_Machine Learning Model Development/` | A Random Forest classifier trained to predict Best Seller status, tuned via GridSearchCV and evaluated with a confusion matrix, classification report, and ROC-AUC |
| 5. Data Visualization & Communication | `Data Visualization and Communication/` | Polished, presentation-ready charts summarizing the key findings |

Supporting files:
- **`Amazon_Sales_Dashboard.xlsx`** — Interactive Excel dashboard built on the cleaned dataset
- **`Final Report.pdf`** — Written summary of the full analysis and conclusions

## Dataset

- **Source:** Amazon product listings collected via web scraping
- **Size:** ~42,700 products, 16 columns after cleaning
- **Key fields:** `title`, `rating`, `number_of_reviews`, `bought_in_last_month`, `current/discounted_price`, `listed_price`, `is_best_seller`, `is_sponsored`, `is_couponed`, `buy_box_availability`, `delivery_details`, `sustainability_badges`, `collected_at`
- Of the ~42,700 listed products, **1,861 (~4.4%) are Best Sellers** and **7,011 (~16.4%) are Sponsored** listings

Cleaning steps included: parsing star ratings and review counts out of raw text, converting "bought in last month" strings (e.g. `5k+`) into numeric estimates, stripping currency symbols from prices, converting badge text (`No Badge` / `Sponsored` / `No Coupon`) into booleans, and parsing collection timestamps.

## Methods

- **EDA:** Price distribution and skewness, Best Seller vs. Regular product comparisons (reviews, price, monthly sales), rating-vs-bestseller crosstabs, correlation matrix, and a t-test comparing ratings between Best Sellers and regular products.
- **Statistical Modeling:** An OLS regression of log-transformed review counts on log-price, rating, sponsorship, and Best Seller status, with a VIF check for multicollinearity and residual plots to validate model assumptions.
- **Machine Learning:** A Random Forest classifier (with class balancing, since Best Sellers are rare) predicting Best Seller status from price, rating, review count, and sponsorship, tuned with `GridSearchCV` and evaluated using precision/recall, a confusion matrix, and ROC-AUC.
- **Visualization:** Custom Amazon-themed charts — a violin plot of price by Best Seller status, a bubble chart relating price, rating, and review volume, and a donut chart breaking down sponsorship rates for Best Sellers vs. regular products.

## Tech Stack

- **Python:** pandas, numpy, matplotlib, seaborn
- **Statistics:** statsmodels (OLS regression, VIF)
- **Machine Learning:** scikit-learn (Random Forest, GridSearchCV, classification metrics)
- **Reporting:** Jupyter Notebook, Excel

## Repository Structure

```
Amazon-Analysis/
├── Datasets and cleaning/
│   ├── amazon_products_sales_data_uncleaned.csv
│   ├── amazon_products_sales_data_cleaned.csv
│   └── amazon_products_sales_data.ipynb
├── Exploratory Data Analysis/
│   ├── eda.ipynb
│   └── *.png (distribution, correlation, time-series charts)
├── _Statistical Modeling/
│   ├── _Statistical Modeling.ipynb
│   ├── report2.pdf
│   └── *.png (residual & Q-Q plots)
├── _Machine Learning Model Development/
│   ├── ml.ipynb
│   └── Confusion Matrix.png
├── Data Visualization and Communication/
│   ├── Data Visualization.ipynb
│   └── *.png (final presentation charts)
├── Amazon_Sales_Dashboard.xlsx
├── Final Report.pdf
└── README.md
```

## Getting Started

```sh
git clone https://github.com/chaturvedimadhav2004-byte/Amazon-Analysis.git
cd Amazon-Analysis
pip install pandas numpy matplotlib seaborn scipy statsmodels scikit-learn jupyter
```

Then open any notebook in Jupyter and run the cells in order. Start with `Datasets and cleaning/amazon_products_sales_data.ipynb` to regenerate the cleaned dataset, or jump straight into `Exploratory Data Analysis/eda.ipynb`, `_Statistical Modeling/_Statistical Modeling.ipynb`, or `_Machine Learning Model Development/ml.ipynb` using the cleaned CSV already provided in each folder.

## Deliverables

- 📊 **`Amazon_Sales_Dashboard.xlsx`** — interactive dashboard for exploring the cleaned data
- 📄 **`Final Report.pdf`** — write-up of the full analysis and findings

## License

No license has been specified for this project yet.

## About Me

**Madhav Chaturvedi**

GitHub: [@chaturvedimadhav2004-byte](https://github.com/chaturvedimadhav2004-byte)

Email: [chaturvedimadhav2004@gmail.com](mailto:chaturvedimadhav2004@gmail.com)

LinkedIn: [madhav-chaturvedi](https://www.linkedin.com/in/madhav-chaturvedi-598868260)

Feel free to reach out or connect if you have questions, feedback, or suggestions about this project!
