# Facet Plot in Seaborn

## Introduction
FacetGrid is a feature in Seaborn that allows you to create multiple plots for different subsets of your data. You can divide your data into subsets based on categories and then apply a plot to each subset, making it an excellent tool for data exploration.

---

## Code Example

```python
import matplotlib.pyplot as plt
import pandas as pd
import seaborn as sns

# Load dataset
data = sns.load_dataset("tips")

# Example 1: Scatter Plot with FacetGrid
fg = sns.FacetGrid(data, col="day", hue="sex")
fg.map(plt.scatter, "total_bill", "tip").add_legend()

plt.show()

# Example 2: Line Plot with FacetGrid
sns.FacetGrid(data, col="time", hue="day").map(sns.lineplot, "total_bill", "tip").add_legend()

plt.show()
```

---

## Explanation

### Example 1: Scatter Plot
1. **FacetGrid**: Creates a grid of plots where each column represents a subset of data based on the `day` column.
   - `col="day"`: Divides the data by the days of the week, creating separate plots for each day.
   - `hue="sex"`: Differentiates the data by gender using different colors.
2. **Map**: Applies a scatter plot to each subset.
   - `plt.scatter`: Creates scatter plots for `total_bill` vs. `tip`.
3. **add_legend()**: Adds a legend to the plot to indicate what the colors represent.

### Example 2: Line Plot
1. **FacetGrid**: Divides the data by `time` (Lunch/Dinner) and applies color differentiation based on the `day`.
2. **Map**: Uses `sns.lineplot` to create line plots for `total_bill` vs. `tip`.
3. **add_legend()**: Adds a legend to the plot.

---

## Available Plots for FacetGrid
You can use the following types of plots inside the `map` function:
- `scatterplot`
- `lineplot`
- `barplot`
- `boxplot`
- `violinplot`
- `stripplot`
- `swarmplot`
- `kdeplot`
- `histplot`

---

## Key Notes
- **FacetGrid** helps visualize data by dividing it into subsets.
- **map()** applies a plot to each subset. You can use various plot types to explore your data.
- **add_legend()** ensures clarity by adding labels to the plot.

