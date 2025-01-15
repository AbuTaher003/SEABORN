# Bar Plot Using Seaborn

### Introduction
This script demonstrates how to create and customize bar plots using the Seaborn library. Additionally, it shows how to load and use a dataset (`penguins`) for visualization.

### Code and Explanation

```python
import matplotlib.pyplot as plt
import pandas as pd
import seaborn as sns

# Load the dataset
data = sns.load_dataset("penguins")
print(data.head())  # Display the first few rows of the dataset

# Basic Bar Plot
sns.barplot(x="island", y="bill_length_mm", data=data, hue="sex", 
            err_kws={"color":'y', "linewidth":5}, dodge=True, alpha=1)

# Explanation:
# - x="island": Sets the x-axis to the 'island' column.
# - y="bill_length_mm": Sets the y-axis to the 'bill_length_mm' column.
# - hue="sex": Differentiates data by 'sex'.
# - err_kws: Customizes error bars with yellow color and width of 5.
# - dodge=True: Ensures bars for each hue are placed side by side.
# - alpha=1: Sets full opacity for the bars.

plt.title("Bar Plot", color='r', fontsize=20)
plt.show()

# Changing Order of Categories
order_1 = ["Biscoe", "Dream", "Torgersen"]  # Custom order for the x-axis
sns.barplot(x="island", y="bill_length_mm", data=data, hue="sex", 
            order=order_1, hue_order=["Female", "Male"])

# Explanation:
# - order: Customizes the order of x-axis categories.
# - hue_order: Customizes the order of hues (Female first, Male second).

plt.show()

# Horizontal Bar Plot
sns.barplot(x="bill_length_mm", y="flipper_length_mm", data=data, orient="h")

# Explanation:
# - orient="h": Creates a horizontal bar plot.

plt.title("Horizontal Bar Plot")
plt.show()

# Adding Grid Style
sns.set(style="darkgrid")  # Changes grid style to 'darkgrid'
```

### Dataset Manipulation Example
We will clean the dataset by removing rows with missing values and calculate the average bill length for each island.

```python
# Removing rows with missing values
cleaned_data = data.dropna()

# Calculate average bill length for each island
average_bill_length = cleaned_data.groupby("island")['bill_length_mm'].mean()
print("Average Bill Length by Island:\n", average_bill_length)
```

### Output Example
```
Average Bill Length by Island:
 island
Biscoe       45.257895
Dream        44.239474
Torgersen    38.950000
Name: bill_length_mm, dtype: float64
```

This output shows the average bill length for penguins on each island after cleaning the dataset.

### Features Covered
1. Creating bar plots with Seaborn.
2. Customizing bar plots with hue, error bars, and transparency.
3. Changing the order of categories on x-axis and hue.
4. Creating horizontal bar plots.
5. Cleaning and manipulating datasets using pandas.


