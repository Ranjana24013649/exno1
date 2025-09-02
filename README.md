# Exno:1
## Data Cleaning Process

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

                    pn=df.fillna(method='ffill')
                    pn

<img width="927" height="745" alt="Screenshot (391)" src="https://github.com/user-attachments/assets/4439b98d-f48e-4cb9-8f4c-d0c942e83b24" />

                    pn=df.fillna(method='bfill')
                    pn

<img width="1010" height="710" alt="Screenshot (392)" src="https://github.com/user-attachments/assets/166d9127-8b74-4156-9999-57ffe5417d1d" />

                    pn=df.fillna({'GENDER':'MALE','NAME':'SRI','ADDRESS':'SVR','M1':6,'M2':5,'M3':7,'M4':8,'TOTAL':'9','AVG':10})
                    pn

<img width="1081" height="715" alt="Screenshot (393)" src="https://github.com/user-attachments/assets/feb9febf-e9d2-442f-9640-81c158930687" />

                    ir=pd.read_csv('iris.csv')
                    ir

<img width="629" height="466" alt="Screenshot (394)" src="https://github.com/user-attachments/assets/8bcbd485-dd66-4cd2-941c-2a9797936546" />

                    pn=ir.describe()
                    pn

<img width="497" height="302" alt="Screenshot (395)" src="https://github.com/user-attachments/assets/f4d71109-8a44-4606-b36f-c5e242b799ba" />

                    import seaborn as sns
                    sns.boxplot(x='sepal_width',data=ir)

<img width="716" height="582" alt="Screenshot (396)" src="https://github.com/user-attachments/assets/0d32be21-f876-4098-b5cd-6b9e1c70006b" />

                    q1=ir.sepal_width.quantile(0.25)
                    q3=ir.sepal_width.quantile(0.75)
                    iq=q3-q1
                    print(iq)

<img width="521" height="143" alt="Screenshot 2025-09-02 091330" src="https://github.com/user-attachments/assets/1a5e76aa-cd39-4202-9f59-6933c66d27d1" />

                    rid=ir[((ir.sepal_width<(q1-1.5*iq))|(ir.sepal_width>(q3+1.5*iq)))]
                    rid['sepal_width']

<img width="402" height="128" alt="Screenshot 2025-09-02 091520" src="https://github.com/user-attachments/assets/a9f48731-a2cb-4c78-b657-95b73bec7878" />

                    pn=ir[~((ir.sepal_width<(q1-1.5*iq))|(ir.sepal_width>(q3+1.5*iq)))]
                    pn

<img width="625" height="550" alt="Screenshot 2025-09-02 091642" src="https://github.com/user-attachments/assets/78b9b7a0-5b7e-41b9-aebf-5b7ba6c48467" />

                    sns.boxplot(x='sepal_width',data=pn)

<img width="880" height="573" alt="image" src="https://github.com/user-attachments/assets/8cfddf3e-9ef3-4258-a060-d5da8df9ba29" />

                    import numpy as np
                    import scipy.stats as stats
                    
                    z=np.abs(stats.zscore(ir['sepal_width']))
                    z

<img width="498" height="279" alt="Screenshot 2025-09-02 091926" src="https://github.com/user-attachments/assets/bf1ecb8b-71e2-4c87-841f-2e89a470f246" />
                    
                    pn=ir[z<3]
                    pn

<img width="661" height="501" alt="Screenshot 2025-09-02 092045" src="https://github.com/user-attachments/assets/e57c8207-591c-4826-89fc-220a4e96d6bd" />


# Result
Thus we have cleaned the data and removed the outliers by detection using IQR and Z-score method.

          
