# 🦄 Unicorn Startups — Exploratory Data Analysis

##  Project Overview

This project explores the patterns behind **unicorn startups worldwide** using a dataset containing information about company valuation, funding, industry, location, financial stage, and investors.

A **unicorn startup** is a privately held company valued at more than **$1 billion**.

The main goal of this analysis is to understand:

* What factors are associated with higher startup valuations?
* How strongly does funding relate to valuation?
* Does the number of investors relate to company valuation?
* Which industries and countries produce the most unicorn companies?
* Which investors appear most frequently across successful startups?

---

##  Dataset

The dataset contains information about **1,500 unicorn companies** and **11 variables**.

### Features

#### Numerical Features

* **Valuation ($B)** — Estimated company market value.
* **Total Raised ($B)** — Total funding raised across all funding rounds.
* **Founded Year** — Year the company was founded.
* **Investors Count** — Number of investors associated with the company.

#### Categorical Features

* Company
* Country
* City
* Industry
* Select Investors
* Financial Stage
* Date Joined

---

##  Target Variable

Initially, **Investors Count** was considered as a potential target variable.

However, exploratory analysis showed that Investors Count has an extremely weak relationship with the other variables, particularly company valuation (**r ≈ 0.02**).

Therefore, **Valuation ($B)** was selected as the target variable because it has a much stronger relationship with important predictors, especially **Total Raised ($B)** (**r = 0.93**).

---

##  Data Cleaning

Several data-quality checks were performed before analysis.

### Data Quality Checks

* No missing values were found.
* No duplicate records were found.
* `Date Joined` was converted into a datetime format.
* Two logically inconsistent records were removed because the company became a unicorn before its founding year.
* No inconsistent category names were detected.

---

## Feature Engineering

The following transformations were performed:

### Joined Year

`Date Joined` was converted into a datetime format and the year was extracted as **Joined Year**.

This allowed analysis of trends between the year a company was founded and the year it became a unicorn.

### Investor Names

The `Select Investors` column contains multiple investor names stored as comma-separated values.

The investor names were split into individual names to allow investor frequency analysis.

---

## 📈 Outlier Analysis

The **IQR (Interquartile Range)** method was used to identify potential outliers.

| Feature         | Outliers |
| --------------- | -------: |
| Valuation       |      195 |
| Total Raised    |      217 |
| Founded Year    |        1 |
| Joined Year     |        9 |
| Investors Count |        0 |

The high valuation and funding outliers were **not removed** because they represent genuine successful unicorn companies rather than data-entry errors.

Keeping these observations provides a more realistic representation of the unicorn startup ecosystem.

---

##  Exploratory Data Analysis

### 1. Valuation and Funding

The strongest relationship in the dataset is between:

**Valuation ($B) ↔ Total Raised ($B)**

with a correlation of:

> **r = 0.931**

This indicates that companies that raise more funding generally tend to have higher valuations.

---

### 2. Founded Year and Joined Year

A strong positive correlation was also found between:

**Founded Year ↔ Joined Year**

> **r = 0.864**

This suggests that newer companies generally became unicorns in more recent years.

---

### 3. Investors Count

Investors Count showed almost no linear correlation with valuation:

> **r ≈ 0.02**

This suggests that simply having more investors does **not necessarily correspond to a higher company valuation** in this dataset.

Therefore, investor **quality and experience** may be more meaningful than simply counting the number of investors.

---

### 4. Valuation Distribution

Most companies have valuations close to the **$1 billion** unicorn threshold.

However, a small number of companies have extremely high valuations, reaching approximately **$149.03B**.

This results in a highly skewed valuation distribution.

---

### 5. Industry Analysis

**FinTech** is the most common industry among the unicorn companies in the dataset.

This highlights the significant role of financial technology in the global startup ecosystem.

---

### 6. Geographic Distribution

The **United States** contains the largest number of unicorn companies, followed by **China** and **India**.

These countries represent major startup ecosystems with large markets and strong technology talent.

---

### 7. Investor Frequency

Some investors appear repeatedly across successful unicorn companies.

Examples include:

* Tiger Global Management
* Thrive Capital
* Google Ventures
* Khosla Ventures
* Coatue Management
* SoftBank Group

This suggests that a relatively small group of experienced investors participates in funding many successful startups.

---

#  Key Findings

1. **Funding is strongly associated with valuation.**
   Total Raised has a very strong positive correlation with Valuation (**r = 0.93**).

2. **Investor count is not a strong indicator of valuation.**
   Investors Count has almost no linear correlation with Valuation (**r ≈ 0.02**).

3. **Valuation is highly skewed.**
   Most unicorns are valued close to $1B, while a small number have exceptionally high valuations.

4. **FinTech dominates the unicorn ecosystem.**
   It contains the largest number of unicorn companies in the dataset.

5. **The United States leads globally.**
   The U.S. has the largest concentration of unicorn companies.

6. **Some investors repeatedly appear in successful startups.**
   Experienced investors such as Tiger Global Management and Thrive Capital appear frequently.

7. **Newer companies tend to become unicorns in more recent years.**
   Founded Year and Joined Year have a strong positive correlation (**r = 0.864**).

8. **High-value outliers are meaningful.**
   Extreme valuations represent genuine high-value businesses and were therefore retained.

---

# 💼 Business Recommendations

### 1. Prioritize Startups With Strong Fundraising Performance

Since funding has a strong relationship with valuation, the amount of capital raised can be considered an important indicator when evaluating startups.

### 2. Focus on High-Growth Industries

Industries such as **FinTech** and **Software Services** produce a significant share of unicorn companies and may represent attractive areas for investment.

### 3. Evaluate Investor Quality Rather Than Quantity

The number of investors alone is not a reliable indicator of company value.

Investors' experience, reputation, and track record may be more useful factors to consider.

### 4. Monitor Emerging Startup Ecosystems

Although the United States dominates the dataset, **China and India** also represent major unicorn ecosystems and should not be overlooked.

### 5. Maintain Data Quality

Cleaning inconsistent records and validating dates before analysis improves the reliability of the resulting business insights.

---

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Jupyter Notebook
* Exploratory Data Analysis
* Statistical Correlation Analysis
* Data Cleaning
* Feature Engineering

---

## 📁 Project Structure

```text
Unicorn-Startups-EDA/
│
├── data/
│   └── unicorn_startups.csv
│
├── notebooks/
│   └── unicorn_startups_eda.ipynb
│
├── presentation/
│   └── Research Findings Presentation.pdf
│
└── README.md
```

---

## Conclusion

This analysis provides an overview of the factors and patterns associated with global unicorn startups.

The most important finding is that **funding has a strong positive relationship with valuation**, while the **number of investors has almost no linear relationship with valuation**.

The analysis also highlights the dominance of **FinTech**, the leading position of the **United States**, and the repeated participation of experienced investors across successful unicorn companies.

Overall, the findings suggest that when evaluating potential unicorns, **fundraising strength, industry, market ecosystem, and investor quality** may provide more useful insights than simply counting the number of investors.
