# Music Streaming Analysis

## Project Description

This project analyzes user music streaming behavior to compare preferences and consumption patterns between two cities: **Springfield** and **Shelbyville**. Using real online music streaming data, we test the hypothesis that user activity differs by both city and day of the week.

## Objective

**Primary Hypothesis:** User activity differs significantly by day of the week and varies between cities.

## Project Structure

### Stage 1: Data Overview
- Load and examine the streaming dataset
- Identify data types and column definitions
- Assess data quality issues

### Stage 2: Data Preprocessing
- **Header Standardization**: Convert column names to lowercase snake_case
- **Missing Values**: Replace missing data in track, artist, and genre with 'unknown'
- **Duplicate Removal**: Remove exact duplicate rows
- **Implicit Duplicates**: Fix inconsistent genre naming (e.g., 'hip', 'hop', 'hip-hop' → 'hiphop')

### Stage 3: Hypothesis Testing
- Compare total streaming activity by city
- Analyze streaming patterns by day of week
- Create a custom function to cross-tabulate city and day combinations
- Validate hypothesis with empirical evidence

## Key Findings

**Hypothesis Confirmed**

- **Springfield** shows significantly higher streaming activity (2-3x more) compared to Shelbyville
- **Friday** is the peak usage day for both cities
- Consistent patterns observed across the three-day sample (Monday, Wednesday, Friday)

## Dataset

**File:** `music_project_en.csv`

**Columns:**
| Column | Type | Description |
|--------|------|-------------|
| user_id | string | User identifier |
| track | string | Song title |
| artist | string | Artist name |
| genre | string | Music genre |
| city | string | User's city |
| time | string | Time track was played |
| day | string | Day of week |


## Methodology

1. **Data Exploration**: Initial assessment of dataset structure and quality
2. **Data Cleaning**: Standardize formats, handle missing data, remove duplicates
3. **Grouping & Aggregation**: Use split-apply-combine pattern for analysis
4. **Cross-tabulation**: Create custom function for multi-dimensional analysis
5. **Interpretation**: Draw conclusions based on empirical evidence
