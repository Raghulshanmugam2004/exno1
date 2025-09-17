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

```
data.dropna(axis=1)
```
# Output



# Result
          <<include your Result here>>
