# Advanced Data Cleaning & Analysis Pipeline

A comprehensive Python-based data processing project demonstrating scalable, parameterized functions for cleaning, validating, and analyzing customer datasets using nested list structures and index-based operations.

## Overview

This project builds a production-ready data cleaning pipeline that transforms raw, unstructured customer data into clean, analysis-ready datasets. It emphasizes reusable functions, proper data handling, and complex filtering logic for real-world business intelligence applications.

## Dataset Structure

Customer data is stored as nested lists in tabular format:

```python
[
  ['customer_id', 'full_name', age, ['category_list'], [spending_list]],
  ...
]
```

**Field Definitions:**
- **user_id** (Index 0): Unique customer identifier (string)
- **user_name** (Index 1): Full name with mixed casing and underscore separators (string)
- **user_age** (Index 2): Customer age as float value (float)
- **fav_categories** (Index 3): Purchase categories in uppercase (list of strings)
- **total_spendings** (Index 4): Spending amounts per category (list of integers)
