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

## Line Plot using Seaborn
```python
import seaborn as sns
import pandas as pd
import matplotlib.pyplot as plt

df = sns.load_dataset("tips")
df
```
![image](https://github.com/varshasharon/EXNO-6-DS/assets/98278161/f9d2e68e-409d-48ad-a69f-bf6291c2103c)

```python
sns.lineplot(x="total_bill", y= "tip", data = df, hue = "sex", linestyle="solid", legend= "auto" )
```
![image](https://github.com/varshasharon/EXNO-6-DS/assets/98278161/af9f01a2-cccd-427a-8c14-aecc0809a431)

## Bar Chart using Seaborn
```python
tips = sns.load_dataset('tips')
avg_total_bill = tips.groupby('day')['total_bill'].mean()
avg_tip = tips.groupby('day')['tip'].mean()

plt.figure(figsize=(8,6))
p1 = plt.bar(avg_total_bill.index, avg_total_bill, label = 'Total Bill', color="sienna")
p2 = plt.bar(avg_tip.index, avg_tip,bottom = avg_total_bill, label = 'Tip',color="coral")

plt.xlabel('Day of the Week')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()

```
![image](https://github.com/varshasharon/EXNO-6-DS/assets/98278161/7689be90-3e5d-403c-9185-4d49ce3c6a9b)

```python
avg_total_bill = tips.groupby('time')['total_bill'].mean()
avg_tip = tips.groupby('time')['tip'].mean()

p1 = plt.bar(avg_total_bill.index, avg_total_bill, label = 'Total Bill', width=0.4,color='wheat')
p2 = plt.bar(avg_tip.index, avg_tip,bottom = avg_total_bill, label = 'Tip', width=0.4, color='lightsalmon')

plt.xlabel('Time of the day')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Time of Day')
plt.legend()
```
![image](https://github.com/varshasharon/EXNO-6-DS/assets/98278161/ef0c1578-c7f8-4ba9-ada0-ddeff79740f3)

```python
dt = sns.load_dataset('tips')
sns.barplot(x='day', y='total_bill',hue='sex',data=dt, palette='rainbow')
plt.xlabel('Day of the week')
plt.ylabel('Total Bill')
plt.title('Totak Bill by Day and Gender')
```
![image](https://github.com/varshasharon/EXNO-6-DS/assets/98278161/ada75646-ceda-4b61-b1cb-90c346c8af68)

## Scatterplot using Seaborn
```python
import seaborn as sns
tip=sns.load_dataset('tips')
sns.scatterplot(x='total_bill', y='tip',hue='sex',data=tips)
plt.xlabel('Total Bill')
plt.ylabel('Tip Amount')
plt.title('Scatter Plot of Total Bill vs. Tip Amount')
```
![image](https://github.com/varshasharon/EXNO-6-DS/assets/98278161/2aacab36-fa14-4e89-8f61-095de8e3843f)

## Histogram using Seaborn
```python
import numpy as np
np.random.seed(0)
marks = np.random.normal(loc=70, scale=10, size=100)

sns.histplot(data=marks, bins=10, kde=True, stat='count', cumulative=False, multiple='stack',color='crimson', element='bars', shrink=0.7)
plt.xlabel('Marks')
plt.ylabel('Density')
plt.title('Histogram of Students Marks')

```
![image](https://github.com/varshasharon/EXNO-6-DS/assets/98278161/4f0019bc-c414-408e-8e8e-91c0cb1a7413)

## Box Plot using Seaborn
```python
tips = sns.load_dataset('tips')
sns.boxplot(x=tips['day'], y=tips['total_bill'], hue=tips['sex'])
```
![image](https://github.com/varshasharon/EXNO-6-DS/assets/98278161/dd41db95-c6eb-411e-b17b-41c335e39aaf)

## Violin Plot using Seaborn
```python
sns.violinplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, palette="Set3", inner="quartile")

plt.xlabel("Day of the week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of total bill by the day and smoker status")
```
![image](https://github.com/varshasharon/EXNO-6-DS/assets/98278161/d5cfc4a8-e733-4953-afe3-0cae67c88f05)

```python
sns.set(style='whitegrid')
tip=sns.load_dataset('tips')
sns.violinplot(x='day', y='tip', data=tip, palette="Set2")
```
![image](https://github.com/varshasharon/EXNO-6-DS/assets/98278161/7c51d4b5-6df4-4d8c-a0e5-59921e21c32e)

```python
sns.set(style='whitegrid')
tip=sns.load_dataset('tips')
sns.violinplot(x='tip', y='day', data=tip, palette="Set3")
```
![image](https://github.com/varshasharon/EXNO-6-DS/assets/98278161/98b67c31-43e6-4e49-93eb-c85047a21cf6)

## KDE Plot
```python
sns.kdeplot(data=tips, x='total_bill', hue='time', multiple='fill', linewidth=3, palette='Set2', alpha=0.8)
```
![image](https://github.com/varshasharon/EXNO-6-DS/assets/98278161/72e99bd1-d7e5-4ceb-8ca0-1258ba136f60)

```python
sns.kdeplot(data=tips, x='total_bill', hue='time', multiple='layer', linewidth=3, palette='Set2', alpha=0.8)
```
![image](https://github.com/varshasharon/EXNO-6-DS/assets/98278161/47495d88-fff2-4b16-a46a-12419d99de2f)

```python
sns.kdeplot(data=tips, x='total_bill', hue='time', multiple='stack', linewidth=3, palette='Set2', alpha=0.8)
```
![image](https://github.com/varshasharon/EXNO-6-DS/assets/98278161/dd1eecf3-0db2-426f-b1d2-9d272fe56db9)

## Heat Map using Seaborn
```python
import numpy as np
data=np.random.randint(low=1, high=100, size=(10,10))
hm=sns.heatmap(data=data,annot=True)
```
![image](https://github.com/varshasharon/EXNO-6-DS/assets/98278161/bc108c2c-4887-4fc0-b8b1-031317166558)


# Result:
Thus, Data Visualization using seaborn python library for the given datas has been performed.
