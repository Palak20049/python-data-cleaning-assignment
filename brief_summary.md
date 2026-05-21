# Assignment: Ecommerce Data Cleaning with Pandas

This is the summary of my data exploration and cleaning assignment on the ecommerce dataset. I used Pandas to load, clean, and save the data.

---

## Dataset Overview

Here is a quick look at the dataset before and after cleaning:

| Metric | Original Dataset (`Combined_dataset.csv`) | Cleaned Dataset (`ecommerce_cleaned.csv`) |
| :--- | :--- | :--- |
| **Row Count** | 1000 rows | 1000 rows |
| **Column Count** | 24 columns | 34 columns (added some columns like price, quantity, total_amount, and split the json columns) |
| **Duplicates** | 0 | 0 |
| **Missing Values** | 2639 missing values | 0 missing values |

---

## Steps Taken

Here is a summary of the steps I took in my Jupyter Notebook and Python script.

### 1. Load the CSV
Loaded the dataset using `pd.read_csv()`.
```python
import pandas as pd
df = pd.read_csv("Ecommerce_extracted/Combined_dataset.csv")
```

### 2. Explore Data
I looked at the data to understand its shape and types:
* `df.head()` and `df.tail()` to see the first and last rows.
* `df.shape` to see the number of rows and columns.
* `df.columns` to see the column names.
* `df.dtypes` to see data types.

### 3. Handle Missing Values
Checked for missing values using `df.isnull().sum()`. 
* Filled the missing `discount` values with `0`.
* Filled missing text columns like `what_customers_said`, `seller_name`, etc. with `"Not Available"`.
* The `videos` column had too many missing values (781 out of 1000), so I just dropped it entirely.
* I found out there are unicode character 9608 in the seller names, so I replaced rows containing that with `"Not Available"`.

```python
df_clean = df.copy()
df_clean["discount"] = df_clean["discount"].fillna(0)
# filled other text columns too...
df_clean = df_clean.drop("videos", axis=1)
```

### 4. Remove Duplicates
Checked for duplicates with `df_clean.duplicated().sum()` and dropped them using `df_clean.drop_duplicates()`. There weren't any in this dataset though.

### 5. Convert Prices
The `final_price` column had text like `"""₹3,995.00"""`. so convert it to a number.
Removed the quotes and commas, then sliced off the first character (the currency symbol) and converted it to float.
```python
df_clean["price"] = df_clean["final_price"].astype(str).str.replace('"', '').str.replace(',', '')
df_clean["price"] = df_clean["price"].str[1:].astype(float)
```

### 6. Create Derived Column
Added a `quantity` column (set to 1) and multiplied it by price to get `total_amount`.
```python
df_clean["quantity"] = 1
df_clean["total_amount"] = df_clean["price"] * df_clean["quantity"]
```

### 7. Clean JSON Columns
Some columns like `amount_of_stars` and `product_details` had dictionary/JSON data in them. I used `pd.json_normalize` and `json.loads` to split them out into their own columns. 
For `amount_of_stars` this gave me columns for 1_star, 2_stars, etc.
For `product_details` this gave me description, material_and_care, and size_and_fit.

### 8. Basic Operations
Filtered the dataset to find products with a rating >= 4.0.
I also selected a subset of columns to make a smaller table for viewing.
```python
high_rated = df_clean[df_clean["rating"] >= 4.0]
selected_cols = ["product_id", "title", "price", "rating", "5_stars", "description"]
small_table = df_clean[selected_cols]
```

### 9. Save Dataset
Finally,saved the cleaned dataset to a new CSV file without the index.
```python
df_clean.to_csv("ecommerce_cleaned.csv", index=False)
```
