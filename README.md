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
```
import pandas as pd
df=pd.read_csv("/content/SAMPLEIDS.csv")
df
```
![image](https://github.com/23006823/exno1/assets/138971409/d4456c7e-a792-43ae-8b1b-7a96bc64161b)
```
import pandas as pd
df=pd.read_csv('/content/SAMPLEIDS.csv')
print(df.info)
```
![image](https://github.com/23006823/exno1/assets/138971409/0c51dd7a-94b3-4633-ad2b-4475a99757d0)
```
import pandas as pd
import pandas as pd
df=pd.read_csv('/content/SAMPLEIDS.csv')
print(df.head(13))
```
![image](https://github.com/23006823/exno1/assets/138971409/173c6e28-bcfc-4f2d-ad7f-c444bb7fb44e)
```
import pandas as pd
print(df.tail(12))
```
![image](https://github.com/23006823/exno1/assets/138971409/afb46144-1e9f-4abd-bf98-9694640ed200)
```
import pandas as pd
print(df.describe)
```
![image](https://github.com/23006823/exno1/assets/138971409/496633b0-5eca-4461-a040-f4882ccb6044)
```
df.isnull().sum()
```
![image](https://github.com/23006823/exno1/assets/138971409/34109320-01f7-4593-aa52-5011666cd538)
```
df.nunique()
```
![image](https://github.com/23006823/exno1/assets/138971409/f94124de-49f1-47b3-b9b2-3abf3276d6de)
```
df.TOTAL.fillna(mn,inplace=True)
df
```
![image](https://github.com/23006823/exno1/assets/138971409/5a4b6e08-9dc2-49c5-a9ec-98d90c9dbbff)
```
min=df.M4.min()
min
```
![image](https://github.com/23006823/exno1/assets/138971409/bd6a9d0b-da21-405b-b1c4-96b9d07555fa)
```
df.M4.fillna(min,inplace=True)
df
```
![image](https://github.com/23006823/exno1/assets/138971409/25a431ab-8478-4064-90f9-218afd04519b)
```
import pandas as pd
import seaborn as sns
age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94]
af=pd.DataFrame(age)
af
```
sns.boxplot(data=af)
```
![image](https://github.com/23006823/exno1/assets/138971409/2dd5b6dc-fe36-4dcf-9e42-aefbc7d417b2)
```
sns.scatterplot(data=af)
```
![image](https://github.com/23006823/exno1/assets/138971409/9028539a-0948-4563-96a3-8d6149fc934e)
```
q1=af.quantile(0.25)
q2=af.quantile(0.50)
q3=af.quantile(0.75)
iqr=q3-q1
iqr
low=q1-1.5*iqr
low
high=q3+1.5*iqr
high
```
![image](https://github.com/23006823/exno1/assets/138971409/88a2c49f-cd4a-4300-a46a-79cd9cbcb4a8)
```
af=af[((af>=low)&(af<=high))]
af
```
![image](https://github.com/23006823/exno1/assets/138971409/937b8131-fe64-4c17-b4c5-b04f6829efc1)
```
af.dropna()
```
![image](https://github.com/23006823/exno1/assets/138971409/107f9627-467d-4910-a752-9f6ba343ebed)
```
sns.boxplot(data=af)
```
![image](https://github.com/23006823/exno1/assets/138971409/1f7981a7-7c44-4575-b581-e28a3b8cc24a)
```
sns.scatterplot(data=af)
```
![image](https://github.com/23006823/exno1/assets/138971409/2748934e-f21e-444a-9f22-707932096c16)
```
data=[1,12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,72,75,78,81,84,87,90,93,96,99,102,105]
df=pd.DataFrame(data)
df
```
![image](https://github.com/23006823/exno1/assets/138971409/b4239794-60c3-4270-8f11-4819665aeb67)
```
import numpy as np
from scipy import stats
z=np.abs(stats.zscore(df))
z
```
![image](https://github.com/23006823/exno1/assets/138971409/0e3146d8-93c6-4e93-829a-3f1c281d523f)
```
# Result
 Thus the given program executed successfully
