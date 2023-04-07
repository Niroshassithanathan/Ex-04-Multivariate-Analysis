# Ex-04-Multivariate-Analysis
# AIM:
To perform Multivariate EDA on the given data set.

# EXPLANATION:
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

# ALGORITHM:
# STEP 1
Import the built libraries required to perform EDA and outlier removal.

# STEP 2
Read the given csv file.

# STEP 3
Convert the file into a dataframe and get information of the data.

# STEP 4
Return the objects containing counts of unique values using (value_counts()).

# STEP 5
Plot the counts in the form of Histogram or Bar Graph.

# STEP 6
Use seaborn the bar graph comparison of data can be viewed.

# STEP 7
Find the pairwise correlation of all columns in the dataframe.corr() .

# STEP 8
Save the final data set into the file.

# PROGRAM:
~~~py
NAME:NIROSHA.S
REG NO:212222230097

import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
data=pd.read_csv("SuperStore.csv")
data

data.head()

data.info()

data.describe()

data.dtypes

data.isnull().sum()

data['Postal Code']=data['Postal Code'].fillna(data['Postal Code'].mode()[0])
data.isnull().sum()

sns.scatterplot(x=data['Country'],y=data['Sales'],data=data)

states=data.loc[:,["Region","Sales"]] 
states=states.groupby(by=["Region"]).sum().sort_values(by="Sales") 
plt.figure(figsize=(17,7)) 
sns.barplot(x=states.index,y="Sales",data=states) 
plt.xticks(rotation = 90) 
plt.xlabel=("REGION")
plt.ylabel=("SALES") 
plt.show()

states=data.loc[:,["State","Sales"]] 
states=states.groupby(by=["State"]).sum().sort_values(by="Sales") 
plt.figure(figsize=(17,7)) 
sns.barplot(x=states.index,y="Sales",data=states) 
plt.xticks(rotation = 90) 
plt.xlabel=("SALES") 
plt.ylabel=("STATES") 
plt.show()

states=data.loc[:,["Category","Sales"]] 
states=states.groupby(by=["Category"]).sum().sort_values(by="Sales") 
plt.figure(figsize=(10,7)) 
sns.barplot(x=states.index,y="Sales",data=states) 
plt.xticks(rotation = 90) 
plt.xlabel=("CATEGORY") 
plt.ylabel=("SALES") 
plt.show()

sns.barplot(data['Postal Code'],data['Ship Mode'],hue=data['Region'])

data.corr()

sns.heatmap(data.corr(),annot=True)
~~~
# OUTPUT:
# DATASET

![ds m3](https://user-images.githubusercontent.com/121418437/230622870-40a0a564-a955-4034-8091-12e16d7ffa40.PNG)

# HEAD()

![ds m4](https://user-images.githubusercontent.com/121418437/230622938-6410f0ea-b434-4721-bf39-9dee7ab3cf72.PNG)

# INFO()

![ds m5](https://user-images.githubusercontent.com/121418437/230622972-207be746-9ac5-4d6f-8d62-0feac4988b7a.PNG)

# DESCRIBE()

![ds m6](https://user-images.githubusercontent.com/121418437/230623015-6b2f5199-4447-4410-a69d-d0bc447c4958.PNG)

# DATATYPE()

![ds m7](https://user-images.githubusercontent.com/121418437/230623059-049b2d0d-965c-4890-97a0-1603fa071510.PNG)

# ISNULL()

![ds m8](https://user-images.githubusercontent.com/121418437/230623090-f7fba32b-3256-4d5e-b953-3f0d40017cf6.PNG)

# Postal code has outliers.

![ds m9](https://user-images.githubusercontent.com/121418437/230623143-1f61d08d-c714-4fe6-9b1d-57180bb7f54e.PNG)

# After removing outliers from Postal Code.

# MULTIVARIATE ANALYSIS
# SCATTER PLOT

![ds m10](https://user-images.githubusercontent.com/121418437/230623340-fda38375-cc0a-4ba7-af16-79ecf3d1f3eb.PNG)

# BARPLOT

![ds m11](https://user-images.githubusercontent.com/121418437/230623369-25e1e72e-d181-4e64-b702-0815a56c9f52.PNG)

# West has more sales than other region.

![ds m12](https://user-images.githubusercontent.com/121418437/230624192-d862111e-af57-428e-9c09-68b9a52aee56.PNG)

# California has more sales than other states.

# SEGMENTATION

![ds m13](https://user-images.githubusercontent.com/121418437/230624299-74540cc2-96ab-4f51-86e1-3ea929627d54.PNG)

Technology has more sales than other category.

# SUBPLOTS

![ds m15](https://user-images.githubusercontent.com/121418437/230624966-4b731fa4-fe33-45a2-96a3-5a196f5b9131.png)

# CORRESSION

![ds m2](https://user-images.githubusercontent.com/121418437/230623646-7e80d109-3c3d-4407-8e59-ba9fca4c67db.png)

# HEATMAP()

![ds m14](https://user-images.githubusercontent.com/121418437/230623960-32ccc0ad-cc91-47eb-9e58-be62e8a37a28.PNG)

# RESULT:
     Hence The Performance of the Multivariate EDA on the given data set is verified.



