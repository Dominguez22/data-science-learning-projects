## Project Description

**Instacart** is an online grocery delivery platform where customers can place orders for home delivery, similar to Uber Eats and DoorDash. This project analyzes a reduced and modified subset of public Instacart ordering data to practice data cleaning and exploratory analysis. The provided dataset has been intentionally reduced and altered (missing values and duplicates introduced) while preserving the original distributions to speed up computations and support learning.

## Project Objective

Perform comprehensive data analysis on Instacart transactions through three stages:
1. **Data Overview** - Load and examine all datasets
2. **Data Preprocessing** - Clean and standardize data (handle duplicates, missing values, data types)
3. **Data Analysis** - Exploratory analysis across easy, intermediate, and advanced tasks

## Dataset Structure

The analysis uses five interconnected CSV tables:

| Table | Description |
|-------|-------------|
| **instacart_orders.csv** | One row per order; contains order timing, sequence, and customer info |
| **products.csv** | One row per product; contains product names and department mappings |
| **order_products.csv** | One row per item in each order; links orders to products |
| **aisles.csv** | Aisle category reference data |
| **departments.csv** | Department category reference data |

### Key Columns

**orders table:**
- `order_id` - Unique order identifier
- `user_id` - Unique customer identifier  
- `order_number` - Sequential order count for that customer
- `order_dow` - Day of week (0=Sunday through 6=Saturday)
- `order_hour_of_day` - Hour of day (0-23)
- `days_since_prior_order` - Days elapsed since previous order

**order_products table:**
- `order_id` - Links to orders
- `product_id` - Links to products
- `add_to_cart_order` - Sequential position in cart
- `reordered` - Binary (1=customer reordered this product, 0=first time)

## Project Stages

### Stage 1: Data Overview
- Load all five datasets
- Examine data types and structure
- Identify initial data quality issues
- **Output:** Summary of dataset characteristics

### Stage 2: Data Preprocessing
**Tasks Completed:**
- Removed 15 duplicate order records
- Handled 1,258 missing product names (filled with 'Unknown')
- Addressed 82,814 missing cart order values (filled with 999)
- Verified data types are appropriate for analysis
- **Output:** Clean, standardized datasets ready for analysis

### Stage 3: Data Analysis

#### Easy Tasks (Level A)
1. Verify order timing values are reasonable (hour: 0-23, day: 0-6)
2. Create histogram of orders by hour of day
3. Create histogram of orders by day of week
4. Analyze distribution of days between orders

#### Intermediate Tasks (Level B)
1. Compare Wednesday vs Saturday ordering patterns (bar charts)
2. Analyze distribution of orders per customer
3. Identify top 20 most frequently ordered products

#### Advanced Tasks (Level C)
1. Analyze products per order distribution
2. Find top 20 most frequently reordered items
3. Calculate product-level reorder rates
4. Calculate customer-level reorder rates
5. Identify top 20 products added first to carts

## Key Findings

- **Peak Shopping Hours:** 7:00 AM - 6:00 PM, with variations by day
- **Peak Shopping Day:** Saturday shows highest order volume
- **Customer Behavior:** Majority of customers are one-time purchasers; repeat customers form a small but valuable segment
- **Most Popular Product:** Bananas (66,050 purchases)
- **Typical Order Size:** Most orders contain 4-10 items
- **Reorder Patterns:** Average reorder rate varies by product type
- **First Item Preference:** Specific products are consistently added first to carts

## Technical Stack

- **Language:** Python 3.x
- **Libraries:** pandas, matplotlib
- **Environment:** Jupyter Notebook
- **Data Format:** CSV

## Skills Demonstrated

- Data loading and inspection (multiple CSV files)
- Data quality assessment and handling
- Missing value imputation strategies
- Duplicate detection and removal
- Data type validation and conversion
- Exploratory Data Analysis (EDA)
- Data visualization (histograms, bar charts)
- Grouping and aggregation operations
- Merge operations between dataframes
- Statistical analysis and calculation
- Multi-level analysis (product-level and customer-level)

## Data Quality Issues Addressed

| Issue | Solution | Rationale |
|-------|----------|-----------|
| Duplicate Orders | Removed 15 exact duplicates | Likely system errors or test data |
| Missing Product Names | Filled with 'Unknown' | All from same aisle/dept (data entry issue) |
| Missing Cart Order Values | Filled with 999 | Represents missing data marker; doesn't affect analysis |
| Implicit Duplicates | Standardized genre naming | Inconsistent spelling in product data |

## How to Run
Note: The provided CSV files use a non-standard format in this exercise (custom separators were used). When loading the data with `pd.read_csv()` you may need to specify `sep` and other arguments. Also, for very large DataFrames use `info(show_counts=True)` to display non-null counts.

1. Ensure dataset files are in `/datasets/` directory:
   - `instacart_orders.csv`
   - `products.csv`
   - `order_products.csv`
   - `aisles.csv`
   - `departments.csv`

2. Open `project_4.ipynb` in Jupyter Notebook

3. Run cells sequentially following the three stages

4. Review visualizations and analysis at each stage

## Expected Output

- **Stage 1:** Dataset information and summary statistics
- **Stage 2:** Before/after comparisons showing data cleaning results
- **Stage 3:** 
  - Multiple histograms and bar charts
  - Comparison visualizations
  - Top-N product lists
  - Reorder rate calculations
  - Customer behavior metrics

## Limitations & Considerations

1. Dataset is a modified version; may not represent real-world distributions exactly
2. Analysis is descriptive, not causal - no statistical significance testing performed
3. Missing values for certain aisle/department combinations treated uniformly
4. Analysis period and customer demographic characteristics unknown
5. External factors (seasonal trends, promotions) not considered

## Future Enhancements

- Seasonal analysis (if dates available)
- Customer segmentation analysis
- Time series forecasting of order trends
- Geographic analysis (if location data available)
- Product affinity analysis (products bought together)
- Cohort analysis of customer lifetime value
- Statistical hypothesis testing

## Author

Created as part of TripleTen Data Science Sprint 4

## License

Educational material - instructional use only

