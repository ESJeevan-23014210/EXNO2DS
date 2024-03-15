# EX.NO-2DS
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

### Name : Jeevan E S
### Reg No : 212223230091

```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
dt=pd.read_csv("/content/titanic_dataset.csv")
dt
```

![1](https://github.com/ESJeevan-23014210/EXNO2DS/assets/147139456/3ad2ffb5-2ce4-4211-9d7b-929a5bced614)

```
dt.info()
```

![2](https://github.com/ESJeevan-23014210/EXNO2DS/assets/147139456/a3985a9e-ca28-4da8-a465-190b7420720b)

```
dt.shape
```

![3](https://github.com/ESJeevan-23014210/EXNO2DS/assets/147139456/7486b526-56b2-4ea2-a184-002c5578478e)

```
dt.set_index("PassengerId",inplace=True)
dt.describe()
```

![4](https://github.com/ESJeevan-23014210/EXNO2DS/assets/147139456/019a0a9d-5b15-4cf6-b78a-e3a400f3c03c)


```
dt.nunique()
```

![5](https://github.com/ESJeevan-23014210/EXNO2DS/assets/147139456/c42b55d8-b63f-4c36-874c-da65f4fcd815)



```
dt["Survived"].value_counts()
```

![6](https://github.com/ESJeevan-23014210/EXNO2DS/assets/147139456/7cd8987b-e801-4252-abdf-eca0dbc752c1)



```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```

![7](https://github.com/ESJeevan-23014210/EXNO2DS/assets/147139456/996f0325-23e2-42ab-b0a2-b79b452e4fb7)



```
sns.countplot(data=dt,x="Survived")
```

![8](https://github.com/ESJeevan-23014210/EXNO2DS/assets/147139456/79a95647-e82d-4ee2-886b-ac26cb5d5403)

```
dt
```


![9](https://github.com/ESJeevan-23014210/EXNO2DS/assets/147139456/9ff732cd-2918-442c-83c9-ed1988178f61)


```
dt.Pclass.unique()
```


![10](https://github.com/ESJeevan-23014210/EXNO2DS/assets/147139456/0e8fc28d-48fc-4a10-acc5-483e9c111a36)


```
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
```


![11](https://github.com/ESJeevan-23014210/EXNO2DS/assets/147139456/77b3f6f7-ab2d-4501-928e-f8503f9d3e29)


```
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
```

![12](https://github.com/ESJeevan-23014210/EXNO2DS/assets/147139456/16a7240d-b40a-42fc-a3a5-68e04f50b177)


```
sns.catplot(x='Survived',hue="Gender",data=dt,kind='count')
```

![13](https://github.com/ESJeevan-23014210/EXNO2DS/assets/147139456/11f61c78-79be-428d-ae93-24cac1a7b4ab)


```
dt.boxplot(column="Age",by="Survived")
```

![14](https://github.com/ESJeevan-23014210/EXNO2DS/assets/147139456/41fcbf61-2b8f-4587-8545-f31bc2704f5e)


```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```

![15](https://github.com/ESJeevan-23014210/EXNO2DS/assets/147139456/a73e8ffa-7e6a-45dc-ad52-cd42b9345c0b)



```
sns.jointplot(x="Age",y="Fare",data=dt)
```

![16](https://github.com/ESJeevan-23014210/EXNO2DS/assets/147139456/2f0fad10-0ae8-460b-bcd7-277ea37fa379)


```
fig,ax1=plt.subplots(figsize=(8,5))
sns.boxplot(ax=ax1,x="Pclass",y="Age",hue="Gender",data=dt)
```

![17](https://github.com/ESJeevan-23014210/EXNO2DS/assets/147139456/87746356-1ba4-4a56-9156-e5eb34737220)


```
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
```

![18](https://github.com/ESJeevan-23014210/EXNO2DS/assets/147139456/f3a88b9f-b20a-42b3-afe2-141f4eeae39d)


```
corr=dt.corr()
sns.heatmap(corr,annot=True)
```

![19](https://github.com/ESJeevan-23014210/EXNO2DS/assets/147139456/79a83e41-bec1-4e80-abc0-e8bd94fe7bbc)



```
sns.pairplot(dt)
```

![20](https://github.com/ESJeevan-23014210/EXNO2DS/assets/147139456/efa49a88-14d0-4d59-9dee-95e57b80cbf3)


# RESULT
Thus,Data Analyzing of the given dataset was successful.
