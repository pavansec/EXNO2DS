# EXNO2DS
# AIM:
      To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
```
 import pandas as pd
 import numpy as np
 import matplotlib.pyplot as plt
df=pd.read_csv("titanic_dataset.csv")
df
```
![image](https://github.com/user-attachments/assets/ed4eec57-9f18-4431-8342-3d3d2ecb5c74)
```
 df.info()
```
![image](https://github.com/user-attachments/assets/709f3b56-ddee-424b-a3cc-13cc13ec77ce)
```
df.shape
```
![image](https://github.com/user-attachments/assets/61be8218-8d1d-4be7-a8a4-c038484da6c9)
```
Categorical data analysis
```
```
 df.nunique()
```
![image](https://github.com/user-attachments/assets/018ee48d-29fc-47f0-8e1a-9831bda08e27)
```
 df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/a1beb8c9-60e1-469a-b554-c5d0a50b273e)
```
 per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
 per
```
![image](https://github.com/user-attachments/assets/6dcb8ed2-ca9e-4b6d-bae5-1bae51e40243)
```
 sns.countplot(data=df,x="Survived")
```
![image](https://github.com/user-attachments/assets/75c082c9-0c2d-4c50-9dba-f1a126f8a7dc)
```
df
```
![image](https://github.com/user-attachments/assets/011c0b04-18d3-41bb-b39e-76d901de4cbf)
```
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/97a12e74-021e-4ad6-a9e2-45ca55ba205e)
```
 df.rename(columns={'Sex':'Gender'},inplace=True)
 df
```
![image](https://github.com/user-attachments/assets/8e96a128-8ee1-4cc2-87fc-8efda8f70d2f)
```
Bivariate Analysis
```
```
 sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/813a6da9-5c6e-4d81-a069-7ba233ce8c65)
```
 sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/user-attachments/assets/3b325f7c-2c55-4044-a3e5-de888d9a9240)
```
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/bb1d9d9a-bc2a-47be-9599-81cfabf47d8a)
```
 sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/user-attachments/assets/26b5b1a2-ee2d-405d-8e64-78f0cdea137d)
```
 sns.jointplot(x="Age",y="Fare",data=df)

```
![image](https://github.com/user-attachments/assets/90e878d5-cd3d-4552-82e9-2f0c53538c23)
```
Multivariate Analysis
```
```
fig, ax1 = plt.subplots(figsize=(8,5))
 plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![image](https://github.com/user-attachments/assets/47561fb0-db1f-4042-a5a1-a9a10a6825b6)
```
 sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/e535b796-b65a-4c94-b605-87334dd04761)
```
Co-relation
```
```
import seaborn as sns
import pandas as pd # Import pandas

# Assuming 'df' is your DataFrame
corr = df.select_dtypes(include=['number']).corr() # Select only numerical columns for correlation calculation
sns.heatmap(corr, annot=True)
```
![image](https://github.com/user-attachments/assets/2302cb6b-2427-4db8-a475-5f99cdad31e1)
```
sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/dbf34ca5-e683-4e03-b76c-15519373f5ff)



# RESULT
 We have performed Exploratory Data Analysis on the given data set successfully
