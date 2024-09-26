
# README: Eat Safe, Love - NoSQL Analysis Project

## Project Overview

This project is designed to explore and analyze the UK Food Standards Agency's food hygiene ratings data using MongoDB and Python. The analysis helps determine key insights for future food safety articles for the Eat Safe, Love magazine.
Split into two key components:

1. **Database and Jupyter Notebook Setup**: Setting up the necessary environment to work with MongoDB.
2. **Data Analysis**: Extracting and analyzing data from the database to gain meaningful insights.

### Technologies Used:
- Python
- MongoDB
- Jupyter Notebooks
- Pandas
- Pymongo

---

## Part 1: Database and Jupyter Notebook Setup

In the first part of the project, we set up a MongoDB database connection and verified that the connection was successful.

Key steps:
```python
# Import dependencies
from pymongo import MongoClient
from pprint import pprint
import pandas as pd

# Create an instance of MongoClient
mongo = MongoClient(port=27017)

# Verify connection by listing databases
print(mongo.list_database_names())
```

This ensures that the MongoDB client is correctly set up, allowing us to perform CRUD operations on the database.

---

## Part 2: Data Analysis

Once the MongoDB setup is complete, we begin analyzing the dataset. The goal is to retrieve and analyze the data from MongoDB to find interesting patterns and answer specific questions about the food establishments.

### 1. Data Aggregation
   Aggregation involves combining multiple pieces of data to create summaries. For example, we can use functions like `mean()`, `sum()`, and `count()` to aggregate data based on certain conditions.
   - Example: Aggregating food safety reports by location to find the total number of reports per region.
   ```python
   # Example of aggregation to count reports by location
   df.groupby('location')['report_id'].count()
   ```

### 2. Filtering
   Filtering allows us to isolate specific rows of data based on certain conditions. This helps in focusing the analysis on a particular subset of the data.
   - Example: Filtering records where food safety scores fall below a threshold.
   ```python
   # Example of filtering unsafe food reports
   unsafe_reports = df[df['safety_score'] < 60]
   ```

### 3. Descriptive Statistics
   Descriptive statistics give a quick overview of the data, summarizing the central tendencies and spread. Functions like `describe()` provide metrics such as the mean, median, min, max, and standard deviation.
   - Example: Generating summary statistics for safety scores.
   ```python
   # Example of descriptive statistics
   df['safety_score'].describe()
   ```

---

## Conclusion

By setting up the MongoDB database and analyzing the data, we were able to efficiently extract insights from the dataset, such as food safety trends. The project demonstrates how MongoDB can be leveraged alongside Python for data analysis tasks.
