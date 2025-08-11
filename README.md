import pandas as pd import numpy as np
import matplotlib.pyplot as plt import seaborn as sns
from scipy import stats
df = pd.read_csv(r"C:\Users\maya0\OneDrive\Desktop\New folder\fashion_boutique_sampl
df.head()
print("Shape:", df.shape)
print("\nDuplicate Rows:", df.duplicated().sum())
df.describe()
df[Vproduct_categoryV].value_counts()
df.select_dtypes(include=VnumberV).corr()
Q1 = df[VpriceV].quantile(0.25) Q3 = df[VpriceV].quantile(0.75)
IQR = Q3 - Q1
outliers = df[(df[VpriceV] < Q1 - 1.5*IQR) | (df[VpriceV] > Q3 + 1.5*IQR)] outliers
sns.histplot(df[VpriceV], kde=True) plt.title("Price Distribution") plt.show()
plt.figure(figsize=(6,4))
sns.countplot(data=df, x=Vproduct_categoryV, order=df[Vproduct_categoryV].value_coun plt.title("Product Category Counts")
plt.show()
