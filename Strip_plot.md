# Strip Plot Notes

A Strip Plot is an essential plot in Seaborn that combines features of both Box Plot and Scatter Plot. It displays data as individual dots spread across the axis. Below is an explanation and examples of the Strip Plot.

### Import Libraries
```python
import matplotlib.pyplot as plt
import seaborn as sns
import pandas as pd
```

### Load Dataset
```python
var = sns.load_dataset("tips")
print(var.head())  # View the first few rows of the dataset
```

### Basic Strip Plot
```python
sns.stripplot(x="day", y="total_bill", data=var, hue="sex", palette="pastel", marker=">")
plt.legend(loc="upper left")  # Change the position of the legend
plt.show()
```

**Explanation:**
- `x="day"`: Displays data based on days.
- `y="total_bill"`: Shows total bill amounts for each day.
- `hue="sex"`: Differentiates data by gender using different colors.
- `palette="pastel"`: Uses pastel colors for the plot.
- `marker=">"`: Changes the marker shape to a triangle.
- `plt.legend(loc="upper left")`: Moves the legend to the upper left corner.

### Manual Marker for Male and Female
Seaborn does not directly support different markers for Male and Female. However, this can be done manually.

```python
m = {"Male": 'o', "Female": '<'}

# Plot for Male
sns.stripplot(x="day", y="total_bill", data=var[var["sex"] == "Male"], marker=m["Male"], color="blue", label="Male")

# Plot for Female
sns.stripplot(x="day", y="total_bill", data=var[var["sex"] == "Female"], marker=m["Female"], color="pink", label="Female")

plt.legend(loc="upper left")  # Change the position of the legend
plt.show()
```

### Single Variable Strip Plot
```python
sns.stripplot(x=var["total_bill"])
plt.show()
```
**Explanation:**
- Using only `x` creates a horizontal Strip Plot.
- Using `y` creates a vertical Strip Plot.

### Additional Parameters
The Strip Plot supports additional parameters:
- `linewidth`: Defines the thickness of the dot borders.
- `edgecolor`: Sets the color of the dot borders.
- `size`: Changes the size of the dots.
- `alpha`: Controls the transparency of the dots.

### Example with Additional Parameters
```python
sns.stripplot(x="day", y="total_bill", data=var, hue="sex", palette="muted", size=8, linewidth=1, alpha=0.7, edgecolor="gray")
plt.legend(loc="lower right")
plt.show()
```

**Key Points:**
1. Strip Plot is useful for displaying data across multiple categories.
2. Parameters like Marker and Alpha allow for further customization.
3. Different markers for Male and Female can be set manually.

