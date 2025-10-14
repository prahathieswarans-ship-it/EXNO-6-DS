# EXNO-6-DS-DATA VISUALIZATION USING SEABORN LIBRARY

# Aim:
  To Perform Data Visualization using seaborn python library for the given datas.

# EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# Algorithm:
STEP 1:Include the necessary Library.

STEP 2:Read the given Data.

STEP 3:Apply data visualization techniques to identify the patterns of the data.

STEP 4:Apply the various data visualization tools wherever necessary.

STEP 5:Include Necessary parameters in each functions.

# Coding and Output:
 Include the necessary coding and corresponding screenshots

import seaborn as sns
import matplotlib.pyplot as plt

x = [1, 2, 3, 4, 5]
y = [3, 6, 2, 7, 1]

sns.lineplot(x=x, y=y)

<img width="725" height="505" alt="image" src="https://github.com/user-attachments/assets/547d8db8-c2be-4cab-801b-209ad57dca21" />



df = sns.load_dataset("tips")

sns.lineplot(x="total_bill", y="tip", data=df, hue="sex", linestyle='solid', legend='auto')

<img width="764" height="533" alt="image" src="https://github.com/user-attachments/assets/80649ba5-e6c2-4910-8bef-3bc3fb5a399c" />


x = [1, 2, 3, 4, 5]

y1 = [3, 5, 2, 6, 1]

y2 = [1, 6, 4, 3, 8]

y3 = [5, 2, 7, 1, 4]

sns.lineplot(x=x, y=y1)

sns.lineplot(x=x, y=y2)

sns.lineplot(x=x, y=y3)

plt.title('Multi-Line Plot')

plt.xlabel('X Label')

plt.ylabel('Y Label')

<img width="752" height="563" alt="image" src="https://github.com/user-attachments/assets/0a1b5406-c4bb-4c1b-afb5-4fefa2aa5a11" />



import seaborn as sns

import matplotlib.pyplot as plt

tips = sns.load_dataset('tips')

avg_total_bill = tips.groupby('day')['total_bill'].mean()

avg_tip = tips.groupby('day')['tip'].mean()

plt.figure(figsize=(8, 6))

p1 = plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill')

p2 = plt.bar(avg_tip.index, avg_tip, bottom=avg_total_bill, label='Tip')

plt.xlabel('Day of the Week')

plt.ylabel('Amount')

plt.title('Average Total Bill and Tip by Day')

plt.legend()


<img width="988" height="785" alt="image" src="https://github.com/user-attachments/assets/76dbd4c6-d835-481f-bb2b-13fb07f86421" />




avg_total_bill = tips.groupby('time')['total_bill'].mean()
avg_tip = tips.groupby('time')['tip'].mean()

p1 = plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill', width=0.4)
p2 = plt.bar(avg_tip.index, avg_tip, bottom=avg_total_bill, label='Tip', width=0.4)

plt.xlabel('Time of Day')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Time of Day')
plt.legend()

<img width="764" height="563" alt="image" src="https://github.com/user-attachments/assets/64458cd9-8811-4abc-97d5-00245eec4986" />




import pandas as pd 

tit = pd.read_csv("titanic_dataset.csv")

tit

<img width="583" height="262" alt="image" src="https://github.com/user-attachments/assets/b8f185a4-b35e-4931-b052-b6552e04751e" />




plt.figure(figsize=(8,5))

sns.barplot(x='Embarked',y='Fare',data=tit, palette='rainbow')

plt.title("Fare of Passenger by Embarked Town")

<img width="764" height="563" alt="image" src="https://github.com/user-attachments/assets/7766cc6c-6266-47ea-b745-4468d2f2961b" />






plt.figure(figsize=(8,5))

sns.barplot(x='Embarked',y='Fare',data=tit, palette='rainbow', hue='Pclass')

plt.title("Fare of Passenger by Embarked Town, Divided by Class")

<img width="988" height="674" alt="image" src="https://github.com/user-attachments/assets/39dc0877-6d0b-4af2-80d0-1c0e0b8c2399" />



import seaborn as sns

tips = sns.load_dataset('tips')

sns.scatterplot(x='total_bill', y='tip', hue='sex', data=tips)

plt.xlabel('Total Bill')

plt.ylabel('Tip Amount')

plt.title('Scatter Plot of Total Bill vs. Tip Amount')



import seaborn as sns

import matplotlib.pyplot as plt # implicitly used by seaborn plots

import numpy as np

import pandas as pd

np.random.seed(1)

num_var = np.random.randn(1000)

num_var = pd.Series(num_var, name = "Numerical Variable")

<img width="659" height="324" alt="image" src="https://github.com/user-attachments/assets/58fa1d07-aedd-4583-9bc4-939b8f5feb5b" />




sns.histplot(data = num_var, kde = True)

<img width="777" height="532" alt="image" src="https://github.com/user-attachments/assets/519ddd81-efaf-49d3-99be-24b8e98ab8ad" />



import seaborn as sns
import pandas as pd
tips = sns.load_dataset('tips')
sns.boxplot(x=tips['day'], y=tips['total_bill'], hue=tips['sex'])

<img width="765" height="532" alt="image" src="https://github.com/user-attachments/assets/beac4d1a-4fbe-48a5-805e-8a490c2966aa" />



sns.boxplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, boxprops={"facecolor": "lightblue", "edgecolor": "darkblue"}, whiskerprops={"color": "black", "linestyle": "--", "linewidth": 1.5}, capprops={"color": "black", "linestyle": "--", "linewidth": 1.5})

<img width="765" height="532" alt="image" src="https://github.com/user-attachments/assets/5e27f4ca-a8bf-453b-b4c1-14543c590ec8" />


sns.boxplot(x='Pclass', y='Age', data=tit, palette='rainbow')
plt.title("Age by Passenger Class, Titanic")

<img width="764" height="563" alt="image" src="https://github.com/user-attachments/assets/32492dc8-ceb0-43a6-aff0-b48b3ccc3df6" />


sns.violinplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6,
               palette="Set3", inner="quartile")
# Add labels and title
plt.xlabel("Day of the Week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")


<img width="764" height="563" alt="image" src="https://github.com/user-attachments/assets/a1b906d4-454e-419d-880c-aeadbdb5ba71" />



import seaborn as sns
sns.set(style = 'whitegrid')
tip = sns.load_dataset('tips')
sns.violinplot(x='day', y='tip', data = tip)


<img width="772" height="542" alt="image" src="https://github.com/user-attachments/assets/7a13f1a1-2d5b-4e3c-9885-399c0f067d3a" />


import seaborn as sns
sns.set(style = 'whitegrid')
tip = sns.load_dataset('tips')
sns.violinplot(x=tip['total_bill'])

<img width="698" height="542" alt="image" src="https://github.com/user-attachments/assets/4a3a47c4-9cc5-4381-9826-3a5a0b67ea6a" />


sns.set(style="whitegrid")

sns.violinplot(x="tip",y="day",data=tip)

<img width="793" height="542" alt="image" src="https://github.com/user-attachments/assets/9c13599f-697a-4af4-b605-c8d805defb50" />




sns.kdeplot(data=tips, x='total_bill', hue='time', multiple='fill', linewidth=3, palette='Set2', alpha=0.8)

<img width="779" height="550" alt="image" src="https://github.com/user-attachments/assets/adb4de90-e84e-4ad7-a2c7-1b1e2957b5ce" />


df = pd.read_csv("supermarket.csv")

df

<img width="454" height="247" alt="image" src="https://github.com/user-attachments/assets/a9d1b0fe-7121-4dae-af51-b97c6b8353b9" />



df.head(10)

<img width="751" height="280" alt="image" src="https://github.com/user-attachments/assets/347cd48b-973e-45af-8f77-442f75e3936a" />

sns.kdeplot(data=mart,x="Total")


<img width="828" height="542" alt="image" src="https://github.com/user-attachments/assets/e5a97fe2-f098-4df1-9a11-9f2491c58813" />


sns.kdeplot(data=mart,x="Unit price")


<img width="803" height="542" alt="image" src="https://github.com/user-attachments/assets/a721e088-449c-4d1c-8fa5-edf4019ab928" />


sns.kdeplot(data=mart)

<img width="779" height="533" alt="image" src="https://github.com/user-attachments/assets/9fb1d4ed-144d-4fab-9a29-edc26a6e88b4" />




sns.kdeplot(data=mart,x="Total",hue="Payment",multiple="stack")

<img width="828" height="542" alt="image" src="https://github.com/user-attachments/assets/8dc0e4ab-50dd-4801-9a29-92152150b3aa" />




sns.kdeplot(data=mart,x="Total",hue="Payment",multiple="stack",linewidth=5,palette="Dark2",alpha=0.5)

<img width="828" height="542" alt="image" src="https://github.com/user-attachments/assets/8fc6aa34-3ce9-4d85-9658-e514ea12cae2" />





data = np.random.randint(1,100,size=(10,10))

hm = sns.heatmap(data)


<img width="702" height="511" alt="image" src="https://github.com/user-attachments/assets/54fb4b80-70ed-44ce-8d9e-986ee5fc1393" />


# Result:
 Include your result here
