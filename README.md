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
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
import pandas as pd
df=pd.read_csv('titanic_dataset.csv')
df
<img width="1039" height="379" alt="image" src="https://github.com/user-attachments/assets/92554dca-d49d-49cc-8130-e0e9d90bd220" />

df.info()
<img width="519" height="489" alt="image" src="https://github.com/user-attachments/assets/9aa91f3d-f414-42eb-8cdf-8a7c3c0e8490" />

df.head()
<img width="1063" height="208" alt="image" src="https://github.com/user-attachments/assets/60be17ed-282c-404e-881c-65d0bf68c10c" />

df.nunique()
<img width="259" height="349" alt="image" src="https://github.com/user-attachments/assets/846c8a38-6ca8-4373-9293-5391eff8a411" />

df["Survived"].value_counts()
<img width="370" height="99" alt="image" src="https://github.com/user-attachments/assets/90fc998b-66d3-4ef7-b0de-f47500f25818" />

sns.countplot(data=df,x="Survived")
<img width="926" height="670" alt="image" src="https://github.com/user-attachments/assets/76b7b9c4-67df-4430-b504-8db547d93c6a" />

df.rename(columns={"Sex" : 'Gender'}, inplace=True)
df
<img width="1035" height="376" alt="image" src="https://github.com/user-attachments/assets/a1353d2e-27b5-4687-a746-d822f0a96656" />

sns.catplot(x="Gender",col="Survived",kind="count", data=df,height=5,aspect=.7)
<img width="1039" height="711" alt="image" src="https://github.com/user-attachments/assets/7d94276d-d284-4096-b24f-84f5fa3a1e89" />

sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
<img width="871" height="744" alt="image" src="https://github.com/user-attachments/assets/f9dd5c78-48d7-4891-9000-cb06899597fa" />

df.boxplot(column="Age",by="Survived")
<img width="851" height="707" alt="image" src="https://github.com/user-attachments/assets/ee8fa9bf-340b-4dd4-8f86-d7703fd71203" />

sns.scatterplot(x=df["Age"],y=df['Fare'])
<img width="891" height="672" alt="image" src="https://github.com/user-attachments/assets/61851529-5b63-4173-9697-1e82f843a338" />

sns.jointplot(x="Age",y="Fare",data=df)
<img width="1092" height="826" alt="image" src="https://github.com/user-attachments/assets/2c4a67ab-0751-44a7-87b1-3161ddc53857" />

fig,ax1=plt.subplots (figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass', y='Age', hue='Gender', data=df)
<img width="1031" height="634" alt="image" src="https://github.com/user-attachments/assets/3ba982b0-e416-45ee-b545-fbc1024a94e1" />

corr = df. select_dtypes (include=['number']). corr()
sns. heatmap(corr,annot=True)
<img width="918" height="742" alt="image" src="https://github.com/user-attachments/assets/e4befb5f-20d0-413d-a994-2b66b00cd4b5" />

sns.catplot(data=df, col="Survived", x="Gender", hue="Pclass",kind="count")
<img width="1037" height="527" alt="image" src="https://github.com/user-attachments/assets/27960ed2-31f6-4931-9545-4605b5f79df4" />

# RESULT
        To perform Exploratory Data Analysis on the given data set is succesfully completed
