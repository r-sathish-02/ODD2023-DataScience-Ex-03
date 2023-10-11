# Ex03-Univariate-Analysis
## AIM:
To read the given data and perform the univariate analysis with different types of plots.

## EXPLANATION:
Univariate analysis is basically the simplest form to analyze data. Uni means one and this means that the data has only one kind of variable. The major reason for univariate analysis is to use the data to describe. The analysis will take data, summarise it, and then find some pattern in the data.

## ALGORITHM:
## Step 1:
Read the given data.

## Step 2:
Get the information about the data.

## Step 3:
Remove the null values from the data.

## Step 4:
Mention the datatypes from the data.

## Step 5:
Count the values from the data.

## Step 6:
Do plots like boxplots,countplot,distribution plot,histogram plot.

## PROGRAM:
```
SATHISH R
212222230138
```
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

df=pd.read_csv("iris.csv")

df.nunique()
```
![image](https://github.com/JoyceBeulah/Ex03-Univariate-Analysis/assets/118343698/4108fa38-69b1-487f-a270-c8d066d8bff6)

```
df.head()
```
![image](https://github.com/JoyceBeulah/Ex03-Univariate-Analysis/assets/118343698/967ad792-c155-42a4-9569-37203c980c3a)

```
df.tail()
```
![image](https://github.com/JoyceBeulah/Ex03-Univariate-Analysis/assets/118343698/30969eea-d208-484a-ac38-78f1ef25cba1)

```
df.iloc[:,4].value_counts()
```
![image](https://github.com/JoyceBeulah/Ex03-Univariate-Analysis/assets/118343698/f78c1d28-1f00-41ec-a01c-b8398221904d)

```
for i in range(0,df.shape[1]):
  print("-----------",df.columns[i],"------------")
  print(df.iloc[:,i].value_counts())
  print("---------------------------------------")
```
![image](https://github.com/JoyceBeulah/Ex03-Univariate-Analysis/assets/118343698/0f935ea1-b869-4002-bd24-a6c298d827d6)
![image](https://github.com/JoyceBeulah/Ex03-Univariate-Analysis/assets/118343698/46d8e700-2b17-4f57-9209-8c71920151e3)
![image](https://github.com/JoyceBeulah/Ex03-Univariate-Analysis/assets/118343698/c9dcd936-6bff-444d-9f0c-167df311d20e)

```
sns.countplot(x='species',data=df)
```
![image](https://github.com/JoyceBeulah/Ex03-Univariate-Analysis/assets/118343698/20b49382-01e2-4701-bba2-3f2e14c45f76)

```
dfv=df.loc[df['species']=='virginica']

plt.plot(dfv['sepal_length'],np.zeros_like(dfv['sepal_length']),'*')
plt.xlabel('sepal length')
plt.show()
##plt.plot(df_setosa['sepal_length'],np.zeros_like(df_setosa['sepal_length']),'o')
```
![image](https://github.com/JoyceBeulah/Ex03-Univariate-Analysis/assets/118343698/c2a09a66-3458-4835-b53a-19c088f96558)

```
dfs=df.loc[df['species']=='setosa']
dfc=df.loc[df['species']=='versicolor']

plt.plot(dfs['sepal_length'],np.zeros_like(dfs['sepal_length']),'*')
plt.plot(dfc['sepal_length'],np.zeros_like(dfc['sepal_length']),'X')
```
![image](https://github.com/JoyceBeulah/Ex03-Univariate-Analysis/assets/118343698/d07d8028-de42-4666-a23e-9f86f445ba25)

```
plt.plot(dfv['sepal_length'],np.zeros_like(dfv['sepal_length']),'o')
plt.plot(dfs['sepal_length'],np.zeros_like(dfs['sepal_length']),'*')
plt.plot(dfc['sepal_length'],np.zeros_like(dfc['sepal_length']),'X')
plt.xlabel('petal_length')
plt.show()
```
![image](https://github.com/JoyceBeulah/Ex03-Univariate-Analysis/assets/118343698/b65cc1f3-a7ce-47ad-b85e-d2f3a6a80afe)

```
plt.plot(dfv['sepal_length'],np.zeros_like(dfv['sepal_length']),'o')
plt.plot(dfs['sepal_length'],np.zeros_like(dfs['sepal_length']),'+')
plt.plot(dfc['sepal_length'],np.zeros_like(dfc['sepal_length']),'-')
plt.xlabel('SEPALLENGTH')
plt.show()
```
![image](https://github.com/JoyceBeulah/Ex03-Univariate-Analysis/assets/118343698/41bf94e5-bdc0-46ff-918a-f1c8cf869dcc)

## RESULT:
The given datasets are read and outliers are detected and are removed using IQR and z-score methods.
