# Data Modeling, Aggregation & Descriptive Analytics

## Learning Objectives

-   Organize data in tables with relationships
-   Perform aggregations and create new features
-   Calculate and interpret descriptive statistics
-   Understand KPIs and correlations
-   Use cross tables for categorical analysis

------------------------------------------------------------------------

# What is Data Modeling?

Data Modeling = Structuring data logically for analysis.

Goals: - Reduce redundancy - Ensure consistency - Enable efficient
queries - Support analysis & reporting

------------------------------------------------------------------------

# Organizing Data in Tables

## Example: Online Shop

### Customers Table

  customer_id   name   city
  ------------- ------ ------

### Orders Table

| order_id \| customer_id \| date \| amount \|

Key Idea: - Each table represents one entity - Rows = observations -
Columns = attributes (features)

------------------------------------------------------------------------

# Relationships Between Tables

Types of relationships: 1. One-to-One (1:1) 2. One-to-Many (1:N) 3.
Many-to-Many (M:N)

Primary Key (PK)\
Foreign Key (FK)

Example: - `customer_id` in Orders → Foreign Key

------------------------------------------------------------------------

# Aggregation

Aggregation = Summarizing data.

Examples: - SUM (total sales) - COUNT (number of orders) - AVG (average
price) - MIN / MAX

Example (SQL):

``` sql
SELECT customer_id, SUM(amount)
FROM orders
GROUP BY customer_id;
```

------------------------------------------------------------------------

# Feature Engineering

Feature Engineering = Creating new meaningful variables.

Examples: - Revenue per customer - Order frequency - Customer lifetime
value - Age from birthdate

Example (Python):

``` python
df["revenue_per_order"] = df["total_revenue"] / df["order_count"]
```

Why important? - Improves predictive models - Makes patterns visible -
Supports KPI tracking

------------------------------------------------------------------------

# Descriptive Statistics

Descriptive statistics summarize data.

Two types: - Central tendency - Dispersion (spread)

Used for: - Data exploration - Business reporting - KPI evaluation

------------------------------------------------------------------------

# Mean, Median, Mode

Mean (Average) Mean = sum(x_i) / n

Median - Middle value - Robust to outliers

Mode - Most frequent value

Example: Data: 2, 3, 3, 4, 100\
Mean = 22.4\
Median = 3\
Mode = 3

------------------------------------------------------------------------

# Standard Deviation & Range

Range = Max - Min

Standard Deviation: Measures spread around the mean.

Large SD → data widely spread\
Small SD → data concentrated

------------------------------------------------------------------------

# Key Performance Indicators (KPIs)

KPI = Quantifiable performance measure.

Examples: - Revenue - Conversion Rate - Customer Retention Rate -
Average Order Value

Good KPIs are: - Measurable - Relevant - Actionable - Time-based

------------------------------------------------------------------------

# Correlation

Correlation measures relationship between variables.

Range: - +1 → strong positive - 0 → no linear relationship - -1 → strong
negative

Important: Correlation ≠ Causation!

------------------------------------------------------------------------

# Cross Tables (Contingency Tables)

Used for categorical variables.

Example:

  Gender   Bought   Not Bought
  -------- -------- ------------

Python Example:

``` python
pd.crosstab(df["gender"], df["purchase"])
```

------------------------------------------------------------------------

# Putting It All Together

Workflow: 1. Model data in tables 2. Define relationships 3. Aggregate
data 4. Engineer features 5. Calculate descriptive statistics 6. Define
KPIs 7. Analyze correlations

------------------------------------------------------------------------

# Practical Exercise

Dataset: Online shop

Tasks: - Calculate total revenue per customer - Compute mean & median
order value - Create a cross table for gender vs purchase - Calculate
correlation between marketing spend & revenue
