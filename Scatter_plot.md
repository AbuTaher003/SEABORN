# Scatter Plot Analysis

This scatter plot visualizes the relationship between penguins' **bill length** and **flipper length**, along with distinctions based on their sex (Male or Female).

### Python Code
```python
import matplotlib.pyplot as plt
import seaborn as sns
import pandas as pd

# Load dataset
var = sns.load_dataset("penguins")

# Data cleaning: Remove rows with missing values
var = var.dropna()

# Scatter plot
plt.figure(figsize=(10, 6))
sns.scatterplot(
    x="bill_length_mm",
    y="flipper_length_mm",
    data=var,
    hue="sex",
    style="sex",
    size="sex",
    sizes=(100, 60),
    palette="Accent",
    alpha=0.8,
    markers={"Male": 'o', "Female": '*'}
)

# Customizations
plt.title("Scatter Plot of Bill Length vs. Flipper Length", fontsize=16, color='blue')
plt.xlabel("Bill Length (mm)", fontsize=12)
plt.ylabel("Flipper Length (mm)", fontsize=12)
plt.legend(title="Sex", title_fontsize=12)
plt.grid(True)

# Show plot
plt.show()
```

### Key Points
- **`x="bill_length_mm"` and `y="flipper_length_mm"`**: Plots the relationship between bill length and flipper length.
- **`hue="sex"`**: Differentiates data points based on penguins' sex with distinct colors.
- **`style="sex"` and `markers={"Male":'o',"Female":'*'}`**: Adds unique marker styles for Male and Female.
- **`size="sex"` and `sizes=(100,60)`**: Adjusts marker sizes according to sex.
- **`palette="Accent"`**: Adds visually appealing colors.
- **`alpha=0.8`**: Sets marker transparency.

### Observations
1. The scatter plot helps identify any relationship between bill length and flipper length. For instance, a linear trend may suggest that longer bills are associated with longer flippers.
2. Male and Female penguins are clearly distinguishable by color, marker style, and size, making it easier to analyze differences or overlaps in their measurements.

This enhanced visualization adds clarity to the dataset while highlighting key features of the penguins' physical measurements.

