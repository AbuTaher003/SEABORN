# Heatmap Plot

```python
import matplotlib.pyplot as plt
import seaborn as sns
import numpy as np
import pandas as pd

# Step 1: Generate Data
# Creating a 1D array of 20 evenly spaced values between 1 and 10, then reshaping it into a 4x5 2D array.
data = np.linspace(1, 10, 20).reshape(4, 5)
print("Generated Data:")
print(data)

# Step 2: Basic Heatmap
# Create a heatmap using the generated 2D array.
sns.heatmap(data, vmin=0, vmax=15, cmap="PuOr", annot=True, annot_kws={'color': 'r', 'fontsize': 10}, cbar=True,
            xticklabels=True, yticklabels=True)

# Adding labels and a title for better understanding.
plt.xlabel("Python")
plt.ylabel("wscube")
plt.title("Heatmap Example", fontsize=15, color="blue")
plt.show()

# Explanation:
# - `vmin` and `vmax` set the minimum and maximum values for the color intensity.
# - `cmap` defines the color palette; 'PuOr' is Purple-Orange.
# - `annot=True` enables the display of numerical values inside the heatmap cells.
# - `annot_kws` customizes the annotation text's appearance, like color and size.
# - `cbar=True` adds a color bar to indicate data value ranges.
# - `xticklabels` and `yticklabels` show or hide axis labels.

# Step 3: Using a Dataset
# Load a dataset and drop non-numerical columns for compatibility with the heatmap.
data = sns.load_dataset("anagrams")
data_cleaned = data.drop(columns=["attnr"], axis=1).head(10)

print("\nCleaned Dataset:")
print(data_cleaned)

sns.heatmap(data_cleaned)
plt.title("Heatmap with Dataset")
plt.show()

# Step 4: Customizing Heatmap
# Create a smaller array for demonstration.
var1 = np.linspace(1, 10, 10).reshape(2, 5)

# Display a heatmap with custom color range and annotations.
sns.heatmap(var1, vmin=0, vmax=12, annot=True, cmap="PuOr")
plt.title("Custom Heatmap")
plt.show()

# Step 5: Adding Custom Annotations
# Define a 2x5 array of string annotations to replace numerical values.
data_labels = np.array([
    ["a0", "a1", "a2", "a3", "a4"],
    ["b0", "b1", "b2", "b3", "b4"]
])

# Display heatmap with custom annotations.
sns.heatmap(var1, vmin=0, vmax=12, cmap="PuOr", annot=data_labels, fmt='s')
plt.title("Heatmap with Custom Annotations")
plt.show()
```

## Key Points:
- **Heatmaps** are primarily used for visualizing numerical data. Always clean datasets to remove non-numerical columns when creating a heatmap.
- **Color Range**: Control the heatmap's intensity using `vmin` and `vmax`.
- **Annotations**: Use `annot=True` to display values inside the cells. Customize these values with a separate annotation array and the `fmt` parameter.
- **Customization**: Modify colors with `cmap`, text appearance with `annot_kws`, and axis labels with `xticklabels`/`yticklabels`.
- **Purpose**: Heatmaps are useful for identifying patterns, trends, and data intensity visually.

