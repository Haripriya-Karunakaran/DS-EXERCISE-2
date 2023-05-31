# EXERCISE-2  OUTLIER DETECTION AND REMOVAL

## Aim: 

To read the given data and detect outliers and remove it.
      
## Explanation: 

Outliers can be detected using visualization, implementing mathematical formulas on the dataset, or using the statistical approach.
     
## Algorithm: 

Step 1: Read the given data.
      
Step 2: Detect the outliers from the data. 
      
Step 3: Remove the outliers from the data.
      
Step 4: Save the required data to the file.
      
You are given bhp.csv which contains property prices in the city of Bangalore, India. You need to examine price_per_sqft column and do following,  

## (1). Remove outliers using IQ. 

## CODE:

import pandas as pd

df = pd.read_csv("/content/bhp.csv")

q1 = df['price_per_sqft'].quantile(0.25)

q3 = df['price_per_sqft'].quantile(0.75)

IQR = q3-q1

df_new=df['price_per_sqft'][((df['price_per_sqft']>=q1-1.5*IQR)&(df['price_per_sqft']<=q3+1.5*IQR))]

## (2)	After removing outliers in step 1, you get a new data frame.  

## CODE:

import pandas as pd

df = pd.read_csv("/content/bhp.csv")

q1 = df['price_per_sqft'].quantile(0.25)

q3 = df['price_per_sqft'].quantile(0.75)

IQR = q3-q1

df_new=df['price_per_sqft'][((df['price_per_sqft']>=q1-1.5*IQR)&(df['price_per_sqft']<=q3+1.5*IQR))]

print(df['price_per_sqft'])

## (3)	use z score of 3 to remove outliers. This is quite similar to IQR and you will get exact same result 

## CODE:

import scipy.stats as stats

df['price_per_sqft']=stats.zscore(df['price_per_sqft'])

print(df['price_per_sqft'])

## (4)	for the data set height_weight.csv find the following  

## (i) Using IQR detect weight outliers and print them. 

import pandas as pd

df = pd.read_csv("/content/height_weight.csv")

q1 = df['weight'].quantile(0.25)

q3 = df['weight'].quantile(0.75)

IQR = q3-q1

df_new=df['weight'][((df['weight']>=q1-1.5*IQR)&(df['weight']<=q3+1.5*IQR))]

print(df['weight'])

## ii)Using IQR, detect height outliers and print them. 

import pandas as pd

df = pd.read_csv("/content/height_weight.csv")

q1 = df['height'].quantile(0.25)

q3 = df['height'].quantile(0.75)

IQR = q3-q1

df_new=df['height'][((df['height']>=q1-1.5*IQR)&(df['height']<=q3+1.5*IQR))]

print(df['height'])

## OUTPUT:

![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-2/assets/126390051/8d3fa3c8-181f-449e-ac5e-ec8391db9e37)

![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-2/assets/126390051/dde943b8-9006-40fa-bb5e-66693277f5f7)

![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-2/assets/126390051/5417ea17-9737-4016-a2d9-1353ce8c1c56)

![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-2/assets/126390051/59729d30-07e6-417d-9e4b-53c008ad2dde)

![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-2/assets/126390051/e0682359-e223-4ac5-9a2c-325f9621f144)

![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-2/assets/126390051/0a949e2b-62c4-4b98-b8ec-41cb2c454ae2)

![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-2/assets/126390051/3b74a38e-a380-43c8-9dbb-0c4bd83c5577)

## RESULT:

Thus, the given data is read, outliers are detected and removed it and then is saved into file

 
