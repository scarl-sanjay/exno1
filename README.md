# NAME: Sanjay S
# REG NO: 212223040184

# Exno:1
Data Cleaning Process

# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

# Coding and Output

 import pandas as pd
df=pd.read_csv("/content/SAMPLEIDS.csv")
df

![image](https://github.com/user-attachments/assets/6c931bec-f2dd-412e-bf39-69e10fb9b101)

df.head()

![image](https://github.com/user-attachments/assets/3fdd618c-cf51-4a96-82c7-6c3b5ae41514)

df.tail(5)

![image](https://github.com/user-attachments/assets/01752776-f117-4458-a207-32cdfa953a76)

df.isnull()

![image](https://github.com/user-attachments/assets/af13e0c7-7010-40a5-841c-8d15186fdd8d)

df.notnull()

![image](https://github.com/user-attachments/assets/ed53472d-df91-46e2-a02e-a94b952cfee4)

df.dropna(axis=0)

![image](https://github.com/user-attachments/assets/d00eb2ab-e057-4166-9f39-160ba63488f5)

df.dropna(axis=1)

![image](https://github.com/user-attachments/assets/22eb8139-94fa-480c-9067-420d59d4e7cf)

df.fillna(0)

![image](https://github.com/user-attachments/assets/11acf4ec-620b-4678-bc08-c54d457c5587)

print(df.shape)

![image](https://github.com/user-attachments/assets/78925415-01f9-4244-a38b-87ce30ccabb9)

IQR:

import pandas as pd
import seaborn as sns
ir=pd.read_csv('/content/iris.csv')
ir

![image](https://github.com/user-attachments/assets/37b345b5-d4f0-4dcc-97a7-e13769d53e72)

ir.describe()

![image](https://github.com/user-attachments/assets/702fd741-6f4a-4e12-839e-3f2bfaabcc1f)

sns.boxplot(x='sepal_width',data=ir)

![image](https://github.com/user-attachments/assets/088f1644-6f79-4618-b1d4-a968a3e2386a)

c1=ir.sepal_width.quantile(0.25)
c3=ir.sepal_width.quantile(0.75)
iq=c3-c1
print(c3)

![image](https://github.com/user-attachments/assets/3d0e3c40-58ae-47eb-8f9a-61dc0f84b3e6)

rid=ir[((ir.sepal_width<(c1-1.5*iq))|(ir.sepal_width>(c3+1.5*iq)))]
rid['sepal_width']

![image](https://github.com/user-attachments/assets/95a69192-a347-4c75-9194-b433237da7d0)

delid=ir[~((ir.sepal_width<(c1-1.5*iq))|(ir.sepal_width>(c3+1.5*iq)))]
delid

![image](https://github.com/user-attachments/assets/6a402d8f-840b-4e29-ae46-7a9a8947377a)

sns.boxplot(x='sepal_width',data=delid)

![image](https://github.com/user-attachments/assets/c38247d0-120d-41db-b74f-34843ef63ef1)

Z SQUARE:

import matplotlib.pyplot as plt
import pandas as pd
import pandas as pd
import numpy as np
import scipy.stats as stats
dataset=pd.read_csv("/content/heights.csv")
dataset

![image](https://github.com/user-attachments/assets/1996efb9-c902-4947-98e3-009474361af2)

df = pd.read_csv("heights.csv")
q1 = df['height'].quantile(0.25)
q2 = df['height'].quantile(0.5)
q3 = df['height'].quantile(0.75)
iqr = q3-q1
iqr

![image](https://github.com/user-attachments/assets/f2f87788-0b35-46b1-a85b-7e9827e28ed1)

low = q1 - 1.5*iqr
low

![image](https://github.com/user-attachments/assets/6a0ad368-1270-4514-ac4f-07e22c7d0e08)


high = q3 + 1.5*iqr
high

![image](https://github.com/user-attachments/assets/597bfa8b-b18f-42ab-badc-54016f6e0485)

df1 = df[((df['height'] >=low)& (df['height'] <=high))]
df1

![image](https://github.com/user-attachments/assets/7a1e3744-195e-462b-9567-d66d5f50812e)

z = np.abs(stats.zscore(df['height']))
z

![image](https://github.com/user-attachments/assets/6c31d1bf-2034-4c79-b62e-0eb5b6cbb071)

 df1 = df[z<3]
 df1

 ![image](https://github.com/user-attachments/assets/dfbdd09a-761c-4626-9225-311f56b5fcff)


# Result
         Thus the Data Cleaning Process and Detecting and Removal of Outliers is executed successfully.  
