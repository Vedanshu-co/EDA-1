# Amazon Products — Exploratory Data Analysis

An exploratory data analysis (EDA) of an Amazon product listings dataset, focused on cleaning messy pricing/rating fields and uncovering trends across product categories, discounts, and customer ratings.

## 📊 Overview

This project walks through a typical EDA workflow on real-world e-commerce data:

- Cleaning inconsistent price and percentage fields (currency symbols, commas, string-typed numbers)
- Handling missing values in ratings and rating counts
- Engineering new features from raw category strings
- Aggregating and visualizing trends across product categories
- Exploring the relationship between discounts and customer satisfaction

## 🗂️ Dataset

The notebook expects an `amazon.csv` file in the project root, containing columns such as:

| Column | Description |
|---|---|
| `product_id`, `product_name` | Product identifiers |
| `category` | Pipe-separated category hierarchy (e.g. `Electronics|Mobiles|Accessories`) |
| `discounted_price`, `actual_price` | Prices in ₹ (as strings) |
| `discount_percentage` | Discount as a string percentage |
| `rating`, `rating_count` | Customer rating and number of reviews |
| `product_link`, `img_link` | URLs |

> Note: the raw dataset is not included in this repo. Place your own `amazon.csv` in the root directory before running the notebook.

## 🧹 Data Cleaning

- Removed `₹`, `,`, and `%` symbols from price and discount columns and converted them to numeric types
- Converted `rating` to numeric, coercing invalid entries and filling missing values with the median
- Cleaned and converted `rating_count` to integer, filling missing values with `0`

## 🛠️ Feature Engineering

- `main_category` / `sub_Category` — extracted from the pipe-separated `category` field
- `discount_amount` — computed as `actual_price - discounted_price`

## 📈 Analysis & Visualizations

- Product count, average rating, average discount, and average discounted price by category
- Total discount amount by main category and sub-category (top & bottom performers)
- Product distribution across main and sub-categories (count plots)
- Discount percentage vs. customer rating (scatter plot)
- Distribution of product ratings (histogram with KDE)
- Top 10 most-reviewed products (bar chart)

### Product Distribution by Main Category
<img width="1379" height="545" alt="image" src="https://github.com/user-attachments/assets/78943699-2133-41cc-b9c3-69f084c01e51" />


### Product Distribution by Sub-Category
<img width="1523" height="545" alt="image" src="https://github.com/user-attachments/assets/38fb721f-3a9c-43c5-9fd7-c7f0ea304f59" />


### Discount Percentage vs. Customer Rating
<img width="567" height="453" alt="image" src="https://github.com/user-attachments/assets/f6f6d2a5-310a-4bc6-8cb4-9ec4fd6ab117" />


### Distribution of Customer Ratings
<img width="571" height="453" alt="image" src="https://github.com/user-attachments/assets/801e2139-43a5-4027-be79-d1412c4761cb" />


### Top 10 Most-Reviewed Products
<img width="2014" height="545" alt="image" src="https://github.com/user-attachments/assets/2389cd44-2f66-47ed-9e23-123fd0942685" />


## 🧰 Tech Stack

- Python
- Pandas / NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook

## 🚀 Getting Started

```bash
# Clone the repo
git clone https://github.com/<your-username>/amazon-eda.git
cd amazon-eda

# Install dependencies
pip install pandas numpy matplotlib seaborn jupyter

# Add your dataset
# (place amazon.csv in the project root)

# Launch the notebook
jupyter notebook Amazon_EDA.ipynb
```

## 📌 Key Findings

*(Fill this in with 2–3 standout insights from your analysis, e.g. which category has the highest average discount, or how rating relates to discount percentage.)*

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
