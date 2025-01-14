# Line Plot with Matplotlib and Seaborn

## Importing Necessary Libraries
```python
import matplotlib.pyplot as plt
import seaborn as sns
import pandas as pd
```

## Creating Data for Line Plot
```python
var = [1, 2, 3, 4, 5, 6, 7]
var_1 = [2, 3, 1, 4, 5, 6, 7]

x_1 = pd.DataFrame({"var": var, "var_1": var_1})
```

## Line Plot with Seaborn
```python
sns.lineplot(x="var", y="var_1", data=x_1)  

# Seaborn requires a dataset to work with. Here, we created a DataFrame using pandas 
# and passed it to the `sns.lineplot` function.

# One advantage of Seaborn is that it automatically adds labels to the x and y axes, 
# unlike Matplotlib, where labels need to be explicitly set.

plt.show()
```

## Line Plot with Matplotlib
```python
plt.plot(var, var_1)  # Matplotlib requires x and y data directly.
plt.show()
```

## Using a Predefined Dataset with Seaborn
```python
y_1 = sns.load_dataset("penguins")  

# The `sns.load_dataset` command loads a predefined dataset from Seaborn's library (sourced from GitHub).
# The dataset is stored in the variable `y_1`.

# Use `.head(20)` to view the first 20 rows for a smaller dataset to work with.
```

## Sample Data
```plaintext
species     island      bill_length_mm    bill_depth_mm   flipper_length_mm  body_mass_g     sex
0   Adelie      Torgersen   39.1             18.7             181.0               3750.0          Male
1   Adelie      Torgersen   39.5             17.4             186.0               3800.0          Female
2   Adelie      Torgersen   40.3             18.0             195.0               3250.0          Female
...
```

## Advanced Line Plot with Seaborn
```python
sns.lineplot(x="bill_length_mm", y="flipper_length_mm", data=y_1, hue="sex", size=50, style="sex",
             palette="pastel", markers=["o", ">"], legend=True, dashes=False) 

# Here, we created a line plot showing the relationship between `bill_length_mm` and `flipper_length_mm`.

# Explanation of Parameters:
# - `hue`: Creates separate lines based on the "sex" column.
# - `size`: Sets the thickness of the lines.
# - `style`: Changes the style of lines based on the "sex" column.
# - `palette`: Defines the colors of the lines. You can find color palettes by searching online.
# - `markers`: Adds markers at data points. We used two markers for Male and Female.
# - `legend`: When True, adds a legend for the plot. Set to False to hide.
# - `dashes`: When False, makes lines solid. When True, creates dashed lines.

plt.title("Line Plot", color='r', fontsize=15)  # Adds a title to the plot.
plt.grid()  # Adds grid lines to the plot.
plt.show()
```

## Key Observations
1. Seaborn makes it easy to customize plots and adds labels automatically.
2. The `hue` parameter is very powerful for creating categorized plots.
3. With Matplotlib, you need to add labels and legends manually, but it gives more control over individual plot elements.
