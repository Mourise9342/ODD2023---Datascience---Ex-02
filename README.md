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

##PROGRAM

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

###OUTPUT:

![264048582-5cfadac2-4cf2-4619-b0b9-27803d2f64c1](https://github.com/Mourise9342/ODD2023---Datascience---Ex-02/assets/120081893/b61725ad-6047-4619-a1d1-c0c69e0bb31f)
![264048949-2665cd96-2268-464a-b305-6786328b3d52](https://github.com/Mourise9342/ODD2023---Datascience---Ex-02/assets/120081893/a47345c2-c4e1-4d0f-9c67-98625c0129cf)
73-4bb6-91c8-68bac69c5c0e](https://github.com/Mourise9342/ODD2023---Datascience---Ex-02/assets/120081893/f3f6a5bc-3cee-431d-bbe1-6e16a3c67bb1)
![264048823-67ea1cdb-3812-4be6-873c-7564e981d6b8](https://github.com/Mourise9342/ODD2023---Datascience---Ex-02/assets/120081893/0b669836-9f8d-4f90-aa49-b753c328f746)
![264049027-5c48f61c-28ba-4742-981e-805b6d7d950a](https://github.com/Mourise9342/ODD2023---Datascience---Ex-02/assets/120081893/5c2a5425-1e48-45c5-a0a1-de1b052241c3)
![264049112-6506543c-4795-4f75-aa39-304026fe81c6](https://github.com/Mourise9342/ODD2023---Datascience---Ex-02/assets/120081893/f228774d-0d33-4366-a61b-c05375c802ae)
![264049187-4ce19043-9500-4fef-a871-0318297af769](https://github.com/Mourise9342/ODD2023---Datascience---Ex-02/assets/120081893/7a00bf78-716d-4709-aaf7-cd5e4bf5719f)
![264049370-0e391fe4-4405-4536-ada5-4362d417ef80](https://github.com/Mourise9342/ODD2023---Datascience---Ex-02/assets/120081893/0c78b325-845f-48bd-803d-f86023aaee5a)
![264049461-c3a02353-e146-4933-bd2f-fc40a4004e48](https://github.com/Mourise9342/ODD2023---Datascience---Ex-02/assets/120081893/253b0951-b584-4792-95a7-fad6b7e92aca)
![264049571-995eec4a-8dc7-4ed8-b6e1-f131d9ad20a9](https://github.com/Mourise9342/ODD2023---Datascience---Ex-02/assets/120081893/2d1e00bd-34ba-4ed4-90ca-ad1270a17c04)
![264049648-a6a88214-f01f-42bf-a65d-24534ad13b38](https://github.com/Mourise9342/ODD2023---Datascience---Ex-02/assets/120081893/edfc2948-5381-4c25-b103-1488cec977f4)
![264049723-1fe40cc1-baed-4f36-9![264049757-053fd045-ff07-423b-8565-0276467e2bab](https://github.com/Mourise9342/ODD2023---Datascience---Ex-02/assets/120081893/46862c8c-4f45-429c-9462-fc12eaecda01)
6b0-3f3b5808a79a](https://github.com/Mourise9342/ODD2023---Datascience---Ex-02/assets/120081893/dbad41ce-56d1-468b-9cc0-93e91a2b32ff)





