
# Sales Data Analytics with NumPy

This project demonstrates how to analyze sales data using NumPy in Python. I generated random sales data for 30 days, compute key statistics, and analyze sales by day and week.

## Author

**Kajola Gbenga Adewale**  
Certified Data Scientist | Certified SQL Programmer | Certified Data Analyst | ML/AI Developer  

Feel free to reach out for questions or collaborations!


## 1. Import NumPy

```python
import numpy as np
```

- Imports the NumPy library as `np`, a standard alias.
- NumPy provides powerful tools for numerical computing and data manipulation.


## 2. Generate Sales Data

```python
# Set random seed for repeatability
np.random.seed(42)

# Generate random sales amounts between $100 and $1000
sales = np.random.randint(100, 1000, size=30)

# Print sales data
print("Sales Data for 30 Days:")
print(sales)
```

- `np.random.seed(42)` sets a fixed seed so that the random numbers generated are the same every time you run the code. This makes your results reproducible.
- `np.random.randint(100, 1000, size=30)` generates an array of 30 random integers between 100 and 999 inclusive, simulating daily sales amounts.
- The two `print` statements output a heading and the array of generated sales values.


## 3. Calculate Total Sales

```python
# Total Sales
total_sales = np.sum(sales)
print(f"Total Sales in the Month: ${total_sales}")
```

- `np.sum(sales)` adds all the daily sales values to get the total sales for the entire 30-day period.
- The total is stored in `total_sales`.
- The `print` statement outputs the total sales amount.


## 4. Calculate Average Daily Sales

```python
# Average Daily Sales
average_sales = np.mean(sales)
print(f"Average Daily Sales: ${average_sales:.2f}")
```

- `np.mean(sales)` calculates the average (mean) of the 30 daily sales values.
- This average is stored in `average_sales`.
- The `print` statement outputs the average daily sales, formatted to two decimal places.


## 5. Find Maximum Sales (Best-Selling Day)

```python
# Maximum Sales (Best-selling day)
max_sales = np.max(sales)
best_day = np.argmax(sales) + 1  # Add 1 because days start at 1
print(f"Best-Selling Day: Day {best_day} with sales of ${max_sales}")
```

- `np.max(sales)` finds the highest sales value in the array.
- `np.argmax(sales)` finds the index (position) of that maximum sales value.
- Since Python indexing starts at 0, we add 1 to get the actual day number (1 to 30).
- The best-selling day and its sales amount are printed.


## 6. Find Minimum Sales (Worst-Selling Day)

```python
# Minimum Sales (Worst-selling day)
min_sales = np.min(sales)
worst_day = np.argmin(sales) + 1
print(f"Worst-Selling Day: Day {worst_day} with sales of ${min_sales}")
```

- `np.min(sales)` finds the lowest sales value in the array.
- `np.argmin(sales)` finds the index of this minimum value.
- Add 1 to convert zero-based index to day number.
- Prints the worst-selling day and its sales amount.


## 7. Identify Days with Above Average Sales

```python
above_average_days = np.where(sales > average_sales)
print(f"Days with Above Average Sales: {above_average_days[0] + 1}")  # +1 because days start at 1
```

- `sales > average_sales` creates a Boolean array where each day is marked True if sales were above average.
- `np.where(sales > average_sales)` returns the indices where this condition is True.
- We access the first element of the tuple returned (`above_average_days[0]`) to get the array of day indices.
- Add 1 to each index to convert to day numbers.
- Prints the list of days where sales were above average.


## 8. Sales on Above Average Days

```python
# Sales on those days:
print("Sales on Above Average Days:")
print(sales[above_average_days])
```

- Uses the indices from `above_average_days` to retrieve sales amounts for those days.
- Prints the sales values of above-average days.


## 9. Reshape Data Into Weeks

```python
# Reshape the 30 days into 5 weeks:
weekly_sales = sales.reshape(5, 6)  # 5 weeks, 6 days per week
print("Weekly Sales Data:")
print(weekly_sales)
```

- Reshapes the 1D array of 30 sales values into a 2D array with 5 rows (weeks) and 6 columns (days per week).
- This structure helps analyze sales data week-by-week.
- Prints the reshaped array.


## 10. Calculate Weekly Totals

```python
# Weekly totals:
week_totals = np.sum(weekly_sales, axis=1)
print("Total Sales per Week:")
print(week_totals)
```

- `np.sum(weekly_sales, axis=1)` sums each row of the 2D array, giving total sales per week.
- Stores the weekly totals in `week_totals`.
- Prints the weekly totals array.


## 11. Identify Best Week

```python
# Best week:
best_week = np.argmax(week_totals) + 1
print(f"Best Week: Week {best_week} with total sales of ${week_totals[best_week-1]}")
```

- Finds the index of the highest weekly total using `np.argmax`.
- Adds 1 to convert zero-based index to human-readable week number.
- Prints the best week number and its total sales amount.


# Summary

This detailed walkthrough covers essential NumPy functions for sales data analysis:

- Generating reproducible random data with `np.random.seed` and `np.random.randint`
- Aggregating data with `np.sum` and `np.mean`
- Finding extremes with `np.max`, `np.min`, `np.argmax`, and `np.argmin`
- Filtering data with `np.where`
- Reshaping data arrays with `.reshape()`

These are fundamental tools for data analysts to extract insights from sales datasets.

In summary, all the above lines of codes can be collated and summarized into:

* Step 1: Import Libraries

* Step 2: Create Synthetic Sales Data

* Step 3: Basic Sales Analysis

* Step 4: Find Days with Above Average Sales

* Step 5: Group Sales into Weeks


# Skills Practiced in This Project

* Generating random data with NumPy

* Summing and averaging arrays

* Finding maximum/minimum and their indices

* Boolean indexing

* Reshaping arrays

* Summing across axes