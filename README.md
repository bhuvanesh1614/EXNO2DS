# EXNO2DS
# AIM:
      Thus  perform Exploratory Data Analysis on the given data set.
      
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
```py
import pandas as pd
df=pd.read_csv('titanic_dataset.csv')
df
```
<img width="1335" height="463" alt="{06F60D8D-899E-49DA-926E-83DD36E3E9E2}" src="https://github.com/user-attachments/assets/f5c837f2-5dfc-48a2-a872-ffa311d0d8c0" />

```py
df.shape
```
<img width="228" height="39" alt="{BE6E149E-2EA8-45FD-8F3E-1D8EB73C052E}" src="https://github.com/user-attachments/assets/49930405-cfca-4b91-9068-93720436f663" />

```py
df.set_index("PassengerId",inplace=True)
df
```
<img width="974" height="329" alt="image" src="https://github.com/user-attachments/assets/7e095b1c-9106-48ed-a714-e6a28cdceba8" />

```py
df.nunique()
```
<img width="328" height="215" alt="{95192315-4646-47CD-A87E-27B2E84ED046}" src="https://github.com/user-attachments/assets/5e04cc78-5d44-4d07-bd81-1f518da824f4" />

```py
df['Sex'].value_counts()
```
<img width="317" height="65" alt="{BF904BD0-382D-4EA5-9BF7-263473164A66}" src="https://github.com/user-attachments/assets/199321c4-6c10-4f31-82ad-c7ef97d7b008" />

```py
df.Survived.unique()
```
<img width="350" height="41" alt="image" src="https://github.com/user-attachments/assets/25f09f14-6942-4f31-b2cf-e0966cd05314" />

```py
df.rename(columns={"Sex":"Gender"},inplace=True)
df
```
<img width="1044" height="320" alt="{ADF23EDD-D510-470E-A516-ACF0E6C40A47}" src="https://github.com/user-attachments/assets/ec63a30a-bc84-4680-9eef-e4215fa09179" />

```py
import seaborn as sns
sns.countplot(data=df)
```
<img width="711" height="447" alt="{8F002615-A734-4C5B-8456-054EDBAAF9F8}" src="https://github.com/user-attachments/assets/0c069a9a-7236-45c3-96d2-ce3a38f53f46" />

```py
sns.countplot(x="Survived",hue="Gender",data=df)
```
<img width="836" height="462" alt="{3D31FF98-9C65-4013-98C5-40C660B8DB59}" src="https://github.com/user-attachments/assets/ff3bd18d-8d01-4a3b-9dc1-c1a582ae17ca" />

```py
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
<img width="768" height="562" alt="{C12D793A-8658-4594-832D-A2610E14F932}" src="https://github.com/user-attachments/assets/2b67f94b-0a38-4c67-849c-d28eb58bb3b5" />

```py
sns.boxplot(data=df)
```
<img width="592" height="404" alt="Screenshot 2025-10-07 114331" src="https://github.com/user-attachments/assets/7de1777a-a553-4b29-a685-47dd5ed4289f" />

```py
df.boxplot(column="Survived",by="Gender")
```
<img width="556" height="422" alt="image" src="https://github.com/user-attachments/assets/257925ce-71cd-4242-85c7-8b7c88b2d48b" />

```py
sns.scatterplot(data=df)
```
<img width="673" height="445" alt="{299ED75F-B2F1-4F68-B46F-A0554B73207D}" src="https://github.com/user-attachments/assets/6e0fae8e-03c7-4024-b614-9fb0b70ed2db" />

```py
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
<img width="759" height="442" alt="{27EA6962-C156-4EF0-BF55-E038B3883A17}" src="https://github.com/user-attachments/assets/acf1cf0c-0880-405d-95e0-8dd4af181717" />

```py
sns.jointplot(x="Age",y='Fare',data=df,kind="kde")
```
<img width="644" height="594" alt="{8A269C8B-E2B5-46A2-B9F8-0514C5980126}" src="https://github.com/user-attachments/assets/e7d04abc-0ff7-43cd-a954-651b6ad67753" />

```py
sns.jointplot(x="Age",y='Fare',data=df,kind="hist")
```

 <img width="852" height="567" alt="image" src="https://github.com/user-attachments/assets/3d5d1e2f-56d6-4487-b8b6-0fd97dc48f8a" />

```py
sns.pairplot(data=df)
```

<img width="1302" height="827" alt="image" src="https://github.com/user-attachments/assets/fb0a30d9-d590-433a-b35d-0d1d0fd475ec" />

```py
corr1=df.select_dtypes(include=['number']).corr()
sns.heatmap(corr1,annot=True)
```

<img width="860" height="434" alt="{D8464C5D-5C8F-456C-BA94-A004D52B9351}" src="https://github.com/user-attachments/assets/662c42a3-2d5d-468e-8221-8610817d46e2" />



# RESULT
        <<INCLUDE YOUR RESULT HERE>>
