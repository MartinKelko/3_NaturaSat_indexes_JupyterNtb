# Visualizing Index Data from NaturaSat with Python

## Description
This Python script reads an Excel file containing various environmental indexes processed by NaturaSat software into a pandas DataFrame. It then visualizes the data using a bar chart with matplotlib, making the analysis of patterns and trends intuitive. The script customizes the chart with specific colors, titles, labels, and a grid for better readability and presentation. This method is particularly useful for researchers and analysts working with environmental and geographical datasets.
https://medium.com/@martin2kelko/data-visualization-of-moisture-indices-in-jupyter-notebook-fed0c9bdfc3b

## How to Use

### Prerequisites
- Ensure you have Python installed on your system.
- Install the necessary Python libraries: `pandas` and `matplotlib`.

```sh
pip install pandas matplotlib

import pandas as pd

# Read the Excel file into a DataFrame
df = pd.read_excel('C:\\NaturaSat_Kelko\\Naturasat_Kelko\\Hores2_march_gps\\NDPI_Hores2_march_gps.xlsx')

# Set Curve_name as the index for easier plotting
df.set_index('Curve_name', inplace=True)

import matplotlib.pyplot as plt

# Plotting with custom colors
ax = df.plot(kind='bar', figsize=(10, 5), color=['blue', 'green', 'orange'])
plt.title('24-03-14 | NDPI - Normalized Difference Pond Index')
plt.xlabel('Curve_name')
plt.ylabel('Values')
plt.xticks(rotation=90)
plt.grid(True)
plt.legend(title='Statistics')
plt.tight_layout()
plt.show()

python script_name.py
