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
import numpy as np
import pandas as pd
data=pd.read_csv("SAMPLEIDS.csv")
data
```
# Output
<img width="1161" height="730" alt="1" src="https://github.com/user-attachments/assets/6a7790de-c4e6-4323-aef0-95fdcc2162a6" />

```
data.head(4)
```
# Output
<img width="1102" height="333" alt="2" src="https://github.com/user-attachments/assets/ede81d43-deb1-4d27-823a-e107245485b7" />

```
data.tail(7)
```
# Output
<img width="1137" height="417" alt="3" src="https://github.com/user-attachments/assets/92d156e5-93a7-49a7-aa94-fdb68c3e46fd" />

```
data.isnull()
```
# Output
<img width="952" height="732" alt="4" src="https://github.com/user-attachments/assets/a63e5e24-0e78-4cec-9563-d852b4498112" />

```
data.notnull
```
# Output
<img width="948" height="701" alt="5" src="https://github.com/user-attachments/assets/dfd20767-586a-4ceb-9fc5-4a029229b332" />

```
data.isnull().sum()
```
# Output
<img width="452" height="627" alt="6" src="https://github.com/user-attachments/assets/8e756b77-eb0e-49df-af59-1dc0aa27ccdf" />

```
data.isnull().any()
```
# Output
<img width="505" height="625" alt="7" src="https://github.com/user-attachments/assets/f70ea6aa-feaa-41cc-a02e-7d05f2f3a0c3" />

```
data.dropna(axis=1)
```
# Output
<img width="621" height="728" alt="8" src="https://github.com/user-attachments/assets/54b2ea8e-5dad-4a72-ad6f-1ea56abd5d1b" />

```
data.dropna(axis=0)
```
# Output
<img width="1085" height="617" alt="9" src="https://github.com/user-attachments/assets/c0666568-ace4-4ebb-959a-466b6029b21d" />

```
data.fillna(0)
```
# Output
<img width="1090" height="702" alt="10" src="https://github.com/user-attachments/assets/3a95c2fe-8220-4e54-8215-51f8c84b12fa" />

```
data.fillna(method="ffill")
```
# Output
<img width="1132" height="722" alt="11" src="https://github.com/user-attachments/assets/95f3d71b-bd81-46e7-b818-c6febfab2e8e" />

```
data.bfill()
```
# Output
<img width="1077" height="722" alt="12" src="https://github.com/user-attachments/assets/3c6f3aa9-37ec-4940-840e-451bc55969c2" />

```
data.fillna({'REGNO':0,'NAME':'PRAVEEN'})
```
# Output
<img width="1082" height="620" alt="13" src="https://github.com/user-attachments/assets/90da88ba-096a-4a5f-ae2c-2b2f151451c4" />
```
ir=pd.read_csv("iris.csv")
ir
```
# Output
<img width="818" height="600" alt="14" src="https://github.com/user-attachments/assets/215eefd6-d59c-4813-ba3e-d9c8f8f1e771" />

```
ir.describe()
```
# Output
<img width="697" height="427" alt="15" src="https://github.com/user-attachments/assets/271e20ef-5e26-4a2f-97ec-3216fde093f8" />

```
import seaborn as sns
sns.boxplot(x="sepal_width",data=ir)
```
# Output
<img width="782" height="665" alt="16" src="https://github.com/user-attachments/assets/8ce26a79-4d5d-40f9-a055-d022280e293c" />
```
q1=ir.sepal_width.quantile(0.25)
q3=ir.sepal_width.quantile(0.75)
iqr=q3-q1
print(iqr)
```
# Output
<img width="636" height="175" alt="17" src="https://github.com/user-attachments/assets/3e7d4d4e-3321-491c-a786-ffd4a969da64" />
```
rid=ir[((ir.sepal_width<(q1-1.5*iqr))|(ir.sepal_width>(q3+1.5*iqr)))]
rid['sepal_width
```
# Output
<img width="785" height="347" alt="18" src="https://github.com/user-attachments/assets/ccf6461d-dd11-401f-89e1-74843aa84abd" />
```
rid=ir[~((ir.sepal_width<(q1-1.5*iqr))|(ir.sepal_width>(q3+1.5*iqr)))]
rid
```
# Output
<img width="768" height="602" alt="19" src="https://github.com/user-attachments/assets/a4e6933c-4db0-40a8-9767-5c92b10ffab0" />
```
rid=ir[((ir.sepal_width>(q1-1.5*iqr))&(ir.sepal_width<(q3+1.5*iqr)))]
rid['sepal_width']
```
# Output
<img width="767" height="643" alt="20" src="https://github.com/user-attachments/assets/1147d2be-670d-452d-b58c-b643efcccc56" />
```
import numpy as np
import scipy.stats as stats
z=np.abs(stats.zscore(ir.sepal_width))
z
```
# Output
<img width="732" height="691" alt="21" src="https://github.com/user-attachments/assets/a0b420e5-b482-46a4-8798-6b111b2c7745" />

# Result
Thus the program executed Successfully.
