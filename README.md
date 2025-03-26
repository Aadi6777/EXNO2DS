# EX NO: 2 DS
# Reg no: 212224230001
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

## CODING AND OUTPUT:

```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns  
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
![image](https://github.com/user-attachments/assets/7ce4fecf-2e76-41ee-8f2e-c12f404b060b)
```
df.info()
```
![image](https://github.com/user-attachments/assets/198b0af4-a286-40f0-a066-c041a2f79c37)

```
df.shape
```
![image](https://github.com/user-attachments/assets/f74f8c8f-4593-4144-b9ed-e22563d678a8)

```
df.set_index("PassengerId",inplace=True)
df.describe()
```
![image](https://github.com/user-attachments/assets/d684de01-719e-4b79-996b-bcc84383c3ee)

```
df.shape
```
![image](https://github.com/user-attachments/assets/cf1f16f7-f5dc-4af5-b7f5-182838dbd335)

```
df.nunique()
```
![image](https://github.com/user-attachments/assets/0979d962-9a1a-4f1d-8161-aa150b333758)

```
 df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/d5d68db1-b097-47d9-bc52-5b6a1a436613)

```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/c95f7796-5a6f-40e8-bed3-c26a7c809638)

```
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/user-attachments/assets/848bee5d-383d-462c-b7af-858f163c234b)

```
df
```
![image](https://github.com/user-attachments/assets/90855b04-f263-40e5-b22b-70623ab636bf)

```
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/e61afe2a-63a0-447d-bb6e-3e5ab9d445ea)

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/e44a4788-52a4-4b64-9b56-963aad47e8b4)

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/f5c739f4-d7fa-4b0b-853e-d8fa16b044d0)

```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/user-attachments/assets/46654825-2452-422d-a336-e9ece839eace)

```
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/f8117598-4b76-4fa8-9e2a-22b6d3ad0d4b)

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/user-attachments/assets/d6b4a751-9c17-492f-bce7-23abd165e5b3)

```
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/user-attachments/assets/8ce4f093-3613-4fde-adb1-0010d3d4805d)

```
 fig, ax1 = plt.subplots(figsize=(8,5))
 plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![image](https://github.com/user-attachments/assets/a8454fd3-5810-4e61-8ae5-581bb00f38a0)

```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/e08c0fc2-ec10-4b7f-a54e-1f1fccb429c9)

```
numerical_df = df.select_dtypes(include=['number'])
corr = numerical_df.corr()
sns.heatmap(corr, annot=True)

```
![image](https://github.com/user-attachments/assets/9ce5e00f-a0d1-4d21-bcfc-81545d720094)

```
 sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/99c75f40-1337-4195-b1de-74b4a2c9162c)


# RESULT:
Thus, the Exploratory Data Analysis on the given data set was performed successfully.
