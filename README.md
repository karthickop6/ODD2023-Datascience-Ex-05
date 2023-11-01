# Ex:05 Feature Generation
## AIM:
To read the given data and perform Feature Generation process and save the data to a file.
## Explanation:
Feature Generation (also known as feature construction, feature extraction or feature engineering) is the process of transforming features into new features that better relate to the target.
## Algorithm:
Step 1: Read the given Data.

Step 2: Clean the Data Set using Data Cleaning Process.

Step 3: Apply Feature Generation techniques to all the feature of the data set.

Step 4: Save the data to the file.
```
Name: Karthick P
Register Number: 212222100021
```
## Program
### Encoding data.csv
```python
import pandas as pd
df=pd.read_csv('Encoding Data.csv')
df.head()
df['ord_2'].unique()
from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
climate = ['Cold','Warm','Hot']
en= OrdinalEncoder(categories = [climate])
df['ord_2']=en.fit_transform(df[["ord_2"]])
df
le = LabelEncoder()
df['Nom_0'] = le.fit_transform(df[["nom_0"]])
df  
from category_encoders import BinaryEncoder
be = BinaryEncoder()
data = be.fit_transform(df['bin_1'])
df = pd.concat([df,data],axis=1)
df
be = BinaryEncoder()
data = be.fit_transform(df['bin_2'])
df = pd.concat([df,data],axis=1)
df
```
### Output:
#### Initial data
![5_1_1](https://github.com/Vasanthamukilan/ODD2023-Datascience-Ex-05/assets/119559694/20227720-0050-4582-9dfd-4bd43105b77a)
#### Unique data
![5_1_2](https://github.com/Vasanthamukilan/ODD2023-Datascience-Ex-05/assets/119559694/575ead4d-1ea9-4fa7-814f-9f47a7819938)
#### Original data
![5_1_3](https://github.com/Vasanthamukilan/ODD2023-Datascience-Ex-05/assets/119559694/b8318e85-3ace-4c81-a858-00467ac5ed7d)
#### Label Encoder
![5_1_4](https://github.com/Vasanthamukilan/ODD2023-Datascience-Ex-05/assets/119559694/2557b8eb-6c1f-46a2-8b59-7cf69152780e)
#### Binary Encoder
![5_1_5](https://github.com/Vasanthamukilan/ODD2023-Datascience-Ex-05/assets/119559694/c9a743c7-0c60-4910-809f-69a0caa8e47f)
![5_1_6](https://github.com/Vasanthamukilan/ODD2023-Datascience-Ex-05/assets/119559694/641461c5-524d-418f-9c2c-3cdfb69260f9)

### Data.csv
```python
import pandas as pd
import numpy as np
from scipy import stats
import seaborn as sns
import matplotlib.pyplot as plt
data=pd.read_csv("/content/data.csv")
df=pd.DataFrame(data)
df
from sklearn.preprocessing import LabelEncoder, OrdinalEncoder
pm=['Hot','Warm','Cold','Very Hot']
e1=OrdinalEncoder(categories=[pm])
e1.fit_transform(df[["Ord_1"]])
df['bo2']=e1.fit_transform(df[["Ord_1"]])
df
le=LabelEncoder()
dfc=df.copy()
dfc['Ord_1']=le.fit_transform(dfc['Ord_1'])
dfc
from sklearn.preprocessing import OneHotEncoder
ohe=OneHotEncoder(sparse=False)
df2=df.copy()
enc=pd.DataFrame(ohe.fit_transform(df2[['City']]))
df2=pd.concat([df2,enc],axis=1)
pd.get_dummies(df2,columns=["City"])
from category_encoders import BinaryEncoder
be = BinaryEncoder()
data = be.fit_transform(dfc['bin_1'])
dfc = pd.concat([dfc,data],axis=1)
dfc
be1 = BinaryEncoder()
data = be1.fit_transform(dfc['bin_2'])
dfc = pd.concat([dfc,data],axis=1)
dfc
```
### Output:
#### Initial data
![5_2_1](https://github.com/Vasanthamukilan/ODD2023-Datascience-Ex-05/assets/119559694/e5c979f4-94c8-4a0e-9503-95aca6979aaa)
![5_2_2](https://github.com/Vasanthamukilan/ODD2023-Datascience-Ex-05/assets/119559694/4787be50-fbe8-4673-bf8c-f0bc7412bf5e)
![5_2_3](https://github.com/Vasanthamukilan/ODD2023-Datascience-Ex-05/assets/119559694/11312c37-1942-435f-9317-04859e062b8e)
#### Label encoder
![5_2_4](https://github.com/Vasanthamukilan/ODD2023-Datascience-Ex-05/assets/119559694/055b1732-89a5-4b88-ae61-22dd2ffb48ab)
#### OneHotEncoder
![5_2_5](https://github.com/Vasanthamukilan/ODD2023-Datascience-Ex-05/assets/119559694/35627fe1-a0ec-49ee-900b-2d5ee61970a1)
#### Binary Encoder
![5_2_6](https://github.com/Vasanthamukilan/ODD2023-Datascience-Ex-05/assets/119559694/5fe1ba94-c9fd-498b-8976-c45f3a494b1b)
![5_2_7](https://github.com/Vasanthamukilan/ODD2023-Datascience-Ex-05/assets/119559694/25b12574-f258-4672-92de-aee7ce3a42a6)
## Result:
The above Feature Generation process has been Executed Seccessfully.
