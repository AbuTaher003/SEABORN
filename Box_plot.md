# Box Plot Notes

This note explains how to create and customize box plots using Seaborn and Matplotlib in Python. It includes detailed code examples and simple explanations for easy understanding.

## Code and Explanation

### Importing Libraries
```python
import matplotlib.pyplot as plt
import seaborn as sns
import pandas as pd
```
We need `matplotlib.pyplot` for plotting, `seaborn` for creating the box plot, and `pandas` for handling datasets.

### Loading the Dataset
```python
var = sns.load_dataset("tips")
print(var.head())
```
The `tips` dataset is a built-in dataset in Seaborn. It contains information about bills, tips, and other related data from a restaurant.

### Creating a Grouped Box Plot
```python
sns.set(style="whitegrid") # Adds a grid to the plot.
sns.boxplot(
    x="day", 
    y="total_bill", 
    data=var, 
    hue="time", # Groups data by 'time' (Lunch or Dinner).
    order=["Fri", "Thur", "Sat", "Sun"], # Specifies the order of days.
    showmeans=True, # Displays the mean value as a marker.
    meanprops={"marker": "+", "markeredgecolor": "y"}, # Customizes the mean marker style.
    linewidth=2, # Sets the line width of the boxes.
    palette="plasma" # Sets the color palette.
)
plt.show()
```
- **Outliers**: The dots outside the box represent outliers (unusual data points that are far from the main data range).
- **Mean**: The `showmeans=True` option displays the mean of the data, and `meanprops` customizes its style.

### Changing the Orientation
```python
sns.set(style="whitegrid")
sns.boxplot(
    y="day", 
    x="total_bill", 
    data=var, 
    hue="time", 
    order=["Fri", "Thur", "Sat", "Sun"], 
    showmeans=True, 
    meanprops={"marker": "+", "markeredgecolor": "y"}, 
    linewidth=2, 
    palette="plasma"
)
plt.show()
```
By swapping the `x` and `y` axes, you can change the orientation of the box plot.

### Creating a Single Box Plot
```python
sns.set(style="whitegrid")
sns.boxplot(x=var["total_bill"])
plt.show()
```
This creates a single box plot for the `total_bill` column.

## Key Points
1. **Outliers**: Represented as dots outside the box.
2. **Mean**: Shown when `showmeans=True`.
3. **Customization**: Use `meanprops` to style the mean marker.
4. **Orientation**: Change the axis to switch between horizontal and vertical box plots.

You can copy the code and run it directly to create box plots. This is useful for visualizing data distributions and identifying outliers. Happy plotting!

