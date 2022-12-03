# EDA

![image](image.jfif)
### This repo seeks to define the various stages involved in exploratory data analysis


### THE STEPS INVOLVED 

1. Preparation
a. Import the dataset and necessary libraries (pandas, NumPy & matplotlib)

b. df= pd.read_csv()- this is to import our data into our library and put it into a data frame.

```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sn 

```

2. Understanding the big picture/understand the variables

a.  use the “df.head()” function of pandas library which returns first five observations of the data set.
Similarly “df.tail()” returns last five observations of the data set.

b. use df.shape() - to find out total number of rows and columns in our data

c. use df.info() - this method prints out information about our dataframe 

Mention the data types. Now, let’s also the columns and their data types. For this, we will use the info() method

d. df.describe() function in pandas is very handy in getting various summary statistics.

This function returns the count, mean, standard deviation, minimum and maximum values and the quantiles of the data.
Any missing value or NaN value is automatically skipped. 
describe() function gives a good picture of the distribution of data.

e. Unique values
You can find the number of unique values in the particular column using unique() function in python

```
df['Pclass'].unique()
df['Survived'].unique()
```

Plot the unique values

Yes, you can visualize the unique values present in the data. For this, we will be using the seaborn library. 

You have to call the sns.countlot() function and specify the variable to plot the count plot
```
sns.countplot(df['Pclass']).unique() 
```

g. #Filter data

df[df['Pclass']==1].head()


3. Dealing with missing data 

a.df.isnull().sum()- 
This helps us find out the total number of rows with missing variables
The below code helps to calculate the percentage of missing values in each column

 ```
(df.isnull().sum()/(len(df)))*100

```

 We can replace some missing values with values we choose eg. mode or mean of the column
Now, Let’s fill the senior management with the mode value.

```mode = df['Senior Management'].mode().values[0]
df['Senior Management']= df['Senior Management'].replace(np.nan, mode)
```
