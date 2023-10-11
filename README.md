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
![ds-ex-3-img-1](https://github.com/r-sathish-02/ODD2023-DataScience-Ex-03/assets/118787261/68917b10-64b3-474a-a7ec-e9c7219a0e8c)


```
df.head()
```
![ds-ex-3-img-2](https://github.com/r-sathish-02/ODD2023-DataScience-Ex-03/assets/118787261/1daa7907-3ff2-4a9d-8417-32455660680a)


```
df.tail()
```
![ds-ex-3-img-3](https://github.com/r-sathish-02/ODD2023-DataScience-Ex-03/assets/118787261/f99141bc-633f-48c9-85cb-6ee973d08d3a)


```
df.iloc[:,4].value_counts()
```
![ds-ex-3-img-4](https://github.com/r-sathish-02/ODD2023-DataScience-Ex-03/assets/118787261/1272799f-b200-41b8-8757-b86d83eb9698)


```
for i in range(0,df.shape[1]):
  print("-----------",df.columns[i],"------------")
  print(df.iloc[:,i].value_counts())
  print("---------------------------------------")
```
![ds-ex-3-img-5](https://github.com/r-sathish-02/ODD2023-DataScience-Ex-03/assets/118787261/065efe99-089b-443c-97ba-8f4eab21c183)

![ds-ex-3-img-6](https://github.com/r-sathish-02/ODD2023-DataScience-Ex-03/assets/118787261/12289dc3-1340-41de-8941-2987a33a823a)

![ds-ex-3-img-7](https://github.com/r-sathish-02/ODD2023-DataScience-Ex-03/assets/118787261/ea000dfd-4345-437f-974a-2714a5720d7f)


```
sns.countplot(x='species',data=df)
```
![ds-ex-3-img-8](https://github.com/r-sathish-02/ODD2023-DataScience-Ex-03/assets/118787261/ab48ad47-b205-40be-9359-5319d7e8a8fa)


```
dfv=df.loc[df['species']=='virginica']

plt.plot(dfv['sepal_length'],np.zeros_like(dfv['sepal_length']),'*')
plt.xlabel('sepal length')
plt.show()
##plt.plot(df_setosa['sepal_length'],np.zeros_like(df_setosa['sepal_length']),'o')
```
![ds-ex-3-img-9](https://github.com/r-sathish-02/ODD2023-DataScience-Ex-03/assets/118787261/73674fb4-01b9-4813-ac57-dad74d47e265)

```
dfs=df.loc[df['species']=='setosa']
dfc=df.loc[df['species']=='versicolor']

plt.plot(dfs['sepal_length'],np.zeros_like(dfs['sepal_length']),'*')
plt.plot(dfc['sepal_length'],np.zeros_like(dfc['sepal_length']),'X')
```
![ds-ex-3-img-10](https://github.com/r-sathish-02/ODD2023-DataScience-Ex-03/assets/118787261/5959f6ef-02ed-45a8-9c35-f41bdb046a06)


```
plt.plot(dfv['sepal_length'],np.zeros_like(dfv['sepal_length']),'o')
plt.plot(dfs['sepal_length'],np.zeros_like(dfs['sepal_length']),'*')
plt.plot(dfc['sepal_length'],np.zeros_like(dfc['sepal_length']),'X')
plt.xlabel('petal_length')
plt.show()
```
![ds-ex-3-img-11](https://github.com/r-sathish-02/ODD2023-DataScience-Ex-03/assets/118787261/a9d47e11-694d-4453-b3a3-00d13d832e7a)


```
plt.plot(dfv['sepal_length'],np.zeros_like(dfv['sepal_length']),'o')
plt.plot(dfs['sepal_length'],np.zeros_like(dfs['sepal_length']),'+')
plt.plot(dfc['sepal_length'],np.zeros_like(dfc['sepal_length']),'-')
plt.xlabel('SEPALLENGTH')
plt.show()
```
![ds-ex-3-img-12](https://github.com/r-sathish-02/ODD2023-DataScience-Ex-03/assets/118787261/614f1209-ca4d-4a29-bf46-ed4b06db588b)


## RESULT:
The given datasets are read and outliers are detected and are removed using IQR and z-score methods.
