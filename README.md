# Exno:1
Data Cleaning Process

# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm
STEP 1: 
Read the given Data

STEP 2: 
Get the information about the data

STEP 3: 
Remove the null values from the data

STEP 4: 
Save the Clean data to the file

STEP 5: 
Remove outliers using IQR

STEP 6: 
Use zscore of to remove outliers

# Coding and Output
```
import pandas as pd
df=pd.read_csv("/content/SAMPLEIDS.csv")
df
```

![image](https://github.com/SJananisenthilkumar/exno1/assets/144871139/cd72e0d8-5477-42fd-9cfe-67f5d92e8f89)

```
print(df.head(7))
```

![image](https://github.com/SJananisenthilkumar/exno1/assets/144871139/be15cc85-6365-41fd-aa39-b8a9ead3eba4)

```
print(df.tail(2))
```

![image](https://github.com/SJananisenthilkumar/exno1/assets/144871139/1423c59e-9eee-44da-8e03-3cc6b9892daa)

```
df.info()
```

![image](https://github.com/SJananisenthilkumar/exno1/assets/144871139/e3f89cc0-fc42-4329-b8bc-52ed31e8c599)

```
print(df.describe())
```

![image](https://github.com/SJananisenthilkumar/exno1/assets/144871139/6b924e2a-fc1d-42fa-bd6c-cc21331cf7f4)

```
df.isnull().sum()
```

![image](https://github.com/SJananisenthilkumar/exno1/assets/144871139/b87ad9e8-4366-4aa7-ae16-c175bc37cf32)

```
df.nunique()
```

![image](https://github.com/SJananisenthilkumar/exno1/assets/144871139/d18a51dd-f0d1-438b-be7e-60227a268317)

```
mn=df.TOTAL.mean()
mn
```

![image](https://github.com/SJananisenthilkumar/exno1/assets/144871139/ab684a33-cfb4-43ea-ad0d-9021ddc5481e)

```
df.TOTAL.fillna(mn,inplace=True)
df
```

![image](https://github.com/SJananisenthilkumar/exno1/assets/144871139/54a1d729-e22b-43fb-84a8-75d1b6a1c78e)

```
min=df.M4.min()
min
```

![image](https://github.com/SJananisenthilkumar/exno1/assets/144871139/a00d3b4f-306b-4652-810a-14ac4f9c3620)

```
df.M4.fillna(min,inplace=True)
df
```

![image](https://github.com/SJananisenthilkumar/exno1/assets/144871139/42a0218b-2653-4a10-a276-03058812e8e5)

```
import pandas as pd
import seaborn as sns
age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94]
af=pd.DataFrame(age)
af
```

![image](https://github.com/SJananisenthilkumar/exno1/assets/144871139/d9f4fa0e-f9ad-4446-b38b-44299b5032b9)

```
sns.boxplot(data=af)
```

![image](https://github.com/SJananisenthilkumar/exno1/assets/144871139/309c3f79-9e66-4c59-85e0-a1db8d1ff168)

```
sns.scatterplot(data=af)
```

![image](https://github.com/SJananisenthilkumar/exno1/assets/144871139/4bf2eca0-9796-4655-a0cd-1cad682d47bd)

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

![image](https://github.com/SJananisenthilkumar/exno1/assets/144871139/18eee6b4-08e8-47c3-b198-bac1661b32ee)

```
af=af[((af>=low)&(af<=high))]
af
```

![image](https://github.com/SJananisenthilkumar/exno1/assets/144871139/46a554f8-1b91-400b-a22d-fc4a06cd3d31)

```
af.dropna()
```

![image](https://github.com/SJananisenthilkumar/exno1/assets/144871139/754b5d9a-daa2-4339-aaad-1ed8a3d5f441)

```
sns.boxplot(data=af)
```

![image](https://github.com/SJananisenthilkumar/exno1/assets/144871139/8167a7d2-adc3-4ad8-bc47-a0e03aad89e9)

```
sns.scatterplot(data=af)
```

![image](https://github.com/SJananisenthilkumar/exno1/assets/144871139/ba49efab-40a6-4d39-8458-fb8556d2f9c3)

```
data=[1,12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,72,75,78,81,84,87,90,93,96,99,102,105]
df=pd.DataFrame(data)
df
```

![image](https://github.com/SJananisenthilkumar/exno1/assets/144871139/f87b7ea9-cde8-49b8-9c33-25ff26edd3be)

```
import numpy as np
from scipy import stats
z=np.abs(stats.zscore(df))
z
```

![image](https://github.com/SJananisenthilkumar/exno1/assets/144871139/1f1cb978-f6ca-40de-a65d-b921076d59c4)

# Result
Thus the given program executed successfully.
