# Ex02-Outlier
You are given bhp.csv which contains property prices in the city of banglore, India. You need to examine price_per_sqft column and do following,

(1) Remove outliers using IQR

(2) After removing outliers in step 1, you get a new dataframe.

(3) use zscore of 3 to remove outliers. This is quite similar to IQR and you will get exact same result

(4) for the data set height_weight.csv find the following

(i) Using IQR detect weight outliers and print them

(ii) Using IQR, detect height outliers and print them

##ALGORITHM

STEP 1
Read the given Data

STEP 2
Remove outliers using IQR

STEP 3
After removing outliers in step 1, you get a new dataframe.

STEP 4
Use zscore of 3 to remove outliers. This is quite similar to IQR and you will get exact same result

STEP 5
For the data set height_weight.csv to find the following; (i) Using IQR detect weight outliers and print them (ii) Using IQR, detect height outliers and print them

```
##PROGRAM

NAME:Mourise jane S
REG NO:212222230085

import pandas as pd
import seaborn as sns

age = [1,3,28,27,25,92,30,39,40,50,26,24,29,94]
af = pd.DataFrame(age)
af
sns.boxplot(data = af)
sns.scatterplot(data = af)

q1 = af.quantile(0.25)
q2 = af.quantile(0.5)
q3 = af.quantile(0.75)
iqr = q3 - q1
iqr

low = q1 - 1.5*iqr
low

high = q3 + 1.5*iqr
high

aq = af[((af>=low) & (af<=high))]
aq.dropna()

sns.boxplot(data = af)

af = af[((af>=low) & (af<=high))]
af.dropna()

sns.boxplot(data = af)

sns.scatterplot(data = af)

sns.scatterplot(data = af)

import pandas as pd
import numpy as np
from scipy import stats
import seaborn as sns

data = {'weight':[12,15,18,21,24,27,30,33,36,39,42,45,51,54,57,60,63,66,69,202,72,75,78,81,84,232,87,90,93,96,99,258]}
df = pd.DataFrame(data)
df

sns.boxplot(data = df)

z = np.abs(stats.zscore(df))
print(df[z['weight']>3])

val = [12,15,18,21,24,27,30,33,36,39,42,45,51,54,57,60,63,66,69,202,72,75,78,81,84,232,87,90,93,96,99,258]

out = []
def d_o(val):
  ts = 3
  n = np.mean(val)
  sd = np.std(val)
  for i in val:
    z = (i-n)/sd
    if np.abs(z)>ts:
      out.append(i)
  return out

op = d_o(val)
op

id = pd.read_csv("iris.csv")
id

sns.boxplot(x = 'sepal_width',data = id)

c1 = id.sepal_width.quantile(0.25)
c3 = id.sepal_width.quantile(0.75)
iq = c3-c1
iq

rid = id[((id.sepal_width<(c1-1.5*iq)) | (id.sepal_width>(c3+1.5*iq)))]
rid['sepal_width']

delid = id[~((id.sepal_width<(c1-1.5*iq)) | (id.sepal_width>(c3+1.5*iq)))]
delid

sns.boxplot(x='sepal_width',data = delid)
```

###OUTPUT:
![264048582-5cfadac2-4cf2-4619-b0b9-27803d2f64c1](https://github.com/Mourise9342/ODD2023---Datascience---Ex-02/assets/120081893/1819a618-21eb-42fa-ae84-89b3ccc7cf78)
![264048779-939c364d-fe73-4bb6-91c8-68bac69c5c0e](https://github.com/Mourise9342/ODD2023---Datascience---Ex-02/assets/120081893/c6aaaf23-eaca-4f72-bc3d-15e4827b2fef)
![264048823-67ea1cdb-3812-4be6-873c-7564e981d6b8](https://github.com/Mourise9342/ODD2023---Datascience---Ex-02/assets/120081893/731416f6-6293-4a1b-9f54-78ae77f80cb0)
![264048949-2665cd96-2268-464a-b305-6786328b3d52](https://github.com/Mourise9342/ODD2023---Datascience---Ex-02/assets/120081893/dc46a5bc-5e07-4d1b-8281-3233fe44e783)
![264049027-5c48f61c-28ba-4742-981e-805b6d7d950a](https://github.com/Mourise9342/ODD2023---Datascience---Ex-02/assets/120081893/9592f814-1d9e-4bb6-8605-018408d00259)
![264049112-6506543c-4795-4f75-aa39-304026fe81c6](https://github.com/Mourise9342/ODD2023---Datascience---Ex-02/assets/120081893/3d6d2104-4bae-4944-97f2-047d5fae427b)
![264049187-4ce19043-9500-4fef-a871-0318297af769](https://github.com/Mourise9342/ODD2023---Datascience---Ex-02/assets/120081893/a12ab27e-9580-4b8f-9edd-40754722951e)
![264049370-0e391fe4-4405-4536-ada5-4362d417ef80](https://github.com/Mourise9342/ODD2023---Datascience---Ex-02/assets/120081893/55dc8176-e0d9-43b4-b989-7b502d7b139b)
![264049461-c3a02353-e146-4933-bd2f-fc40a4004e48](https://github.com/Mourise9342/ODD2023---Datascience---Ex-02/assets/120081893/fc80f1c7-9bf0-4d94-ac9f-668d9dc75b75)
![264049571-995eec4a-8dc7-4ed8-b6e1-f131d9ad20a9](https://github.com/Mourise9342/ODD2023---Datascience---Ex-02/assets/120081893/113727cb-0521-4a06-927b-e39fd8000cd9)
![264049648-a6a88214-f01f-42bf-a65d-24534ad13b38](https://github.com/Mourise9342/ODD2023---Datascience---Ex-02/assets/120081893/aa031ebf-3843-4edd-a885-3639918305dc)
![264049723-1fe40cc1-baed-4f36-96b0-3f3b5808a79a](https://github.com/Mourise9342/ODD2023---Datascience---Ex-02/assets/120081893/08fa14c4-b04a-4d27-a7de-290859c600b5)
![264049757-053fd045-ff07-423b-8565-0276467e2bab](https://github.com/Mourise9342/ODD2023---Datascience---Ex-02/assets/120081893/124013a6-95b7-4a2b-88b7-d9c43af0cbd7)

Result:

Hence the given set of data is read and the outliers are removed using the IQR method and Zscore method.







