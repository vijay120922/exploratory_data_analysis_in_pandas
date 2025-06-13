# 🌍 World Population Data - Exploratory Data Analysis in Pandas

This project performs Exploratory Data Analysis (EDA) on a dataset containing global population statistics using Pandas, Matplotlib, and Seaborn.

---

## 📦 Dataset

- File: world_population.csv
- Contains population data for various countries and continents, including:
  - 2020 Population
  - World Population Percentage
  - Continent, etc.

---

## 🧰 Libraries Used

- pandas
- numpy
- matplotlib.pyplot
- seaborn

---

## 📊 EDA Steps Performed

✅ Step 1: Load and View Dataset
----------------------------------
df = pd.read_csv("world_population.csv")

✅ Step 2: Set Float Display Format
----------------------------------
pd.set_option('display.float_format', '{:.2f}'.format)

✅ Step 3: Dataset Overview
-----------------------------
df.info()
df.describe()
df.isnull().sum()
df.nunique()

✅ Step 4: Sort Top 10 Countries by Population Percentage
----------------------------------------------------------
df.sort_values(by='World Population Percentage', ascending=False).head(10)

✅ Step 5: Correlation Matrix (Heatmap)
-----------------------------------------
numeric_df = df.select_dtypes(include='number')
sns.heatmap(numeric_df.corr(), annot=True, cmap='coolwarm')
plt.title("Correlation Matrix (Numeric Features)")
plt.show()

✅ Step 6: Average Population by Continent
--------------------------------------------
df2 = df.groupby('Continent').mean(numeric_only=True).sort_values(by="2020 Population", ascending=False)
df2.plot()

✅ Step 7: Transposed Plot (Metric-wise across Continents)
-----------------------------------------------------------
df3 = df2.transpose()
df3.plot()

✅ Step 8: Boxplot for Outlier Detection
-----------------------------------------
df.boxplot()

---

## 📈 Visualizations

- Heatmap showing correlation between numeric features
- Line plot comparing average 2020 population by continent
- Transposed plot showing metric trends
- Boxplot identifying distribution and outliers

---

## 🧪 Summary

This notebook helps understand:
- Population distribution across continents
- Feature relationships
- Summary statistics and data quality

---

## 📌 License

For educational and exploratory purposes.
