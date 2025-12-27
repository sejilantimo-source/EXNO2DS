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
import seaborn as sns
df=pd.read_csv("titanic_dataset.csv")
df
```
## OUTPUT
<img width="1642" height="572" alt="image" src="https://github.com/user-attachments/assets/a494968a-50b3-47c8-9e42-387abe8ea4a7" />


## CODING
```
df.info()
```

## OUTPUT
<img width="537" height="468" alt="image" src="https://github.com/user-attachments/assets/b69877bb-92c7-4eaf-b04f-fe685440bee7" />


## CODING
```
df.dtypes
```
## OUTPUT
<img width="342" height="620" alt="image" src="https://github.com/user-attachments/assets/7ec4ccef-9462-48f8-9743-e795fbe78ed8" />

## CODING
```
df.value_counts()
```
## OUTPUT
<img width="1687" height="660" alt="image" src="https://github.com/user-attachments/assets/f7bdad1d-69b6-49e7-b85e-e19e06fa664a" />

## CODING
```
df['Age'].value_counts()
```
## OUTPUT
<img width="270" height="660" alt="image" src="https://github.com/user-attachments/assets/6a5eb173-d390-4a77-a51c-d27194c5a826" />


## CODING
```
df.shape
```
## OUTPUT
<img width="175" height="57" alt="image" src="https://github.com/user-attachments/assets/f4c8f2b7-9604-4736-b9d6-2faddd54e9b0" />


## CODING
```
df.set_index("PassengerId",inplace=True)
df.describe()
```
## OUTPUT
<img width="965" height="415" alt="image" src="https://github.com/user-attachments/assets/7af6e553-0be9-4624-b067-90af355dd91b" />


## CODING
```
df.nunique()
```
## OUTPUT
<img width="351" height="582" alt="image" src="https://github.com/user-attachments/assets/c195474c-216f-4c22-af37-6308984ea95d" />

## CODING
```
sns.countplot(data=df,x="Survived")
```
## OUTPUT
<img width="882" height="623" alt="image" src="https://github.com/user-attachments/assets/472847c2-4405-4632-a7de-ef05bf0a1b11" />


## CODING
```
df.Pclass.unique()
```
## OUTPUT
<img width="257" height="47" alt="image" src="https://github.com/user-attachments/assets/89c276d0-c202-4ceb-94b0-54666d37857e" />

## CODING
```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```

## OUTPUT
<img width="1271" height="517" alt="image" src="https://github.com/user-attachments/assets/9378f668-f0e9-4a13-89e1-1e7df252f109" />

## CODING
```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
## OUTPUT
<img width="1050" height="712" alt="image" src="https://github.com/user-attachments/assets/a3b07269-1fbc-4019-80f3-79060b584c23" />



## CODING
```
df.boxplot(column="Age",by="Survived")
```

## OUTPUT
<img width="840" height="666" alt="image" src="https://github.com/user-attachments/assets/48ba44c9-1760-4551-bfe7-31a55e324034" />

## CODING
```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```

## OUTPUT
<img width="868" height="635" alt="image" src="https://github.com/user-attachments/assets/c24db781-9611-493c-8e85-92d828322286" />


## CODING
```
fig, ax1 =plt.subplots(figsize=(8,5))
plt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
## OUTPUT
<img width="1045" height="627" alt="image" src="https://github.com/user-attachments/assets/7133aa76-b0ed-4a9f-a00f-f248ba3d1873" />

## CODING
```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
## OUTPUT
<img width="1547" height="703" alt="image" src="https://github.com/user-attachments/assets/f85f403a-4fe6-4965-a65e-09065d94fe32" />


## CODING
```
corr = df.select_dtypes(include=np.number).corr()
sns.heatmap(corr,annot=True)
```

## OUTPUT
<img width="796" height="613" alt="image" src="https://github.com/user-attachments/assets/168cb4e1-289b-47fa-b84a-9522f605c87c" />



        

# RESULT
        Thus the dataset value is found
