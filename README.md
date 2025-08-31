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
<img width="1045" height="724" alt="Screenshot (382)" src="https://github.com/user-attachments/assets/94f97519-c688-4c4b-bcba-5bca17aa36f8" />

pn=df.head()
pn
<img width="1058" height="253" alt="image" src="https://github.com/user-attachments/assets/5e86c789-b37c-485e-a500-dc887dfd008d" />

pn=df.tail()
pn
<img width="1025" height="216" alt="image" src="https://github.com/user-attachments/assets/3eb1a9c9-97a1-4c85-adfb-f546d43ff21d" />

pn=df.isnull()
pn

<img width="1081" height="728" alt="image" src="https://github.com/user-attachments/assets/b51bf878-8776-41a1-82f5-70fc935e7d08" />

pn=df.isnull().sum()
pn

<img width="729" height="306" alt="image" src="https://github.com/user-attachments/assets/207575a6-3dfb-4b22-a292-97e206404c5f" />

pn=df.isnull().any()
pn
<img width="973" height="302" alt="image" src="https://github.com/user-attachments/assets/62adaac7-9ee7-4f6b-b4ad-99d27fd1322c" />

pn=df.dropna(axis=0)
pn

<img width="1049" height="483" alt="image" src="https://github.com/user-attachments/assets/2b41b6f7-467a-4b46-8252-9910e22a55aa" />

pn=df.dropna(axis=1)
pn

<img width="453" height="696" alt="image" src="https://github.com/user-attachments/assets/f0ea6766-8808-4a9e-80db-6eb78ab5a71b" />

pn=df.fillna(6)
pn

<img width="1081" height="725" alt="Screenshot (388)" src="https://github.com/user-attachments/assets/870c2171-9f62-487d-ae24-14a51ff7ddc2" />





# Result
          <<include your Result here>>
