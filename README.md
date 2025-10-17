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
```
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
x = [1, 2, 3, 4, 5]
y = [3, 6, 2, 7, 1]
plt.figure(figsize=(8, 5))
sns.lineplot(x=x, y=y)
plt.title('Simple Line Plot using Seaborn')
plt.xlabel('X-Values')
plt.ylabel('Y-Values')
plt.grid(True)
plt.show()
```
<img width="833" height="529" alt="Screenshot 2025-10-16 233039" src="https://github.com/user-attachments/assets/1d638bc5-0375-49c0-ba93-757730f2b6b2" />

```
x = [1, 2, 3, 4, 5]
y1 = [3, 5, 2, 6, 1]
y2 = [1, 6, 4, 3, 8]
y3 = [5, 2, 7, 1, 4]
data = pd.DataFrame({'X': x, 'Y1': y1, 'Y2': y2, 'Y3': y3})
data_long = data.melt('X', var_name='Series', value_name='Y_Value')

plt.figure(figsize=(8, 5))
sns.lineplot(data=data_long, x='X', y='Y_Value', hue='Series', style='Series', markers=True, dashes=False)
plt.title('Multiple Line Plots using Seaborn')
plt.xlabel('X-Value')
plt.ylabel('Y-Value')
plt.legend(title='Data Series')
plt.grid(True)
plt.show()
```
<img width="858" height="538" alt="Screenshot 2025-10-16 233047" src="https://github.com/user-attachments/assets/1bd51b24-1b97-4e1e-acbe-00abf2d443be" />

```
tips = sns.load_dataset('tips')
plt.figure(figsize=(8, 5))
sns.barplot(x='day', y='total_bill', hue='sex', data=tips, palette='viridis')

plt.xlabel('Day of the Week')
plt.ylabel('Total Bill (Average)')
plt.title('Average Total Bill by Day and Gender')
plt.show()
```
<img width="856" height="531" alt="Screenshot 2025-10-16 233053" src="https://github.com/user-attachments/assets/a7925c87-4728-4ded-b44c-688a7c448fe7" />

```
tit = sns.load_dataset('titanic')
tit.head()
```
<img width="958" height="203" alt="Screenshot 2025-10-16 233101" src="https://github.com/user-attachments/assets/4816aa2d-82ab-4672-96db-0cafb5bdbf2c" />

```
plt.figure(figsize=(8,5))
sns.barplot(x='embark_town', y='fare', data=tit, palette='rainbow', errorbar=None)
plt.title('Fare of Passenger by Embarked Town')
plt.xlabel('Embarked Town')
plt.ylabel('Fare (Average)')
plt.show()
```
<img width="827" height="533" alt="Screenshot 2025-10-16 233108" src="https://github.com/user-attachments/assets/faa0a1b6-c8de-4fef-b176-a21d7e4bfc70" />

```
plt.figure(figsize=(8,5))
sns.barplot(x='embark_town', y='fare', data=tit, palette='rainbow', hue='pclass', errorbar=None)
plt.title('Fare of Passenger by Embarked Town, Divided by Class')
plt.xlabel('Embarked Town')
plt.ylabel('Fare (Average)')
plt.legend(title='Passenger Class')
plt.show()
```
<img width="859" height="541" alt="Screenshot 2025-10-16 233114" src="https://github.com/user-attachments/assets/15d8f7a8-7566-4b94-855d-d0734bb7b064" />

```
import seaborn as sns
plt.figure(figsize=(8, 5))
sns.scatterplot(x='total_bill', y='tip', data=tips, hue='time', style='smoker')

plt.xlabel('Total Bill')
plt.ylabel('Tip Amount')
plt.title('Scatter Plot of Total Bill vs. Tip Amount')
plt.show()
```
<img width="896" height="547" alt="Screenshot 2025-10-16 233122" src="https://github.com/user-attachments/assets/48166058-f9ab-4a44-a980-81005e6416d8" />

```
plt.figure(figsize=(8, 5))
sns.violinplot(x='pclass', y='age', data=tit, hue='sex', split=True, palette='Pastel1')
plt.title('Age Distribution by Passenger Class and Sex (Violin Plot)')
plt.xlabel('Passenger Class')
plt.ylabel('Age')
plt.legend(title='Sex')
plt.show()
```
<img width="882" height="533" alt="Screenshot 2025-10-16 233128" src="https://github.com/user-attachments/assets/28d288a4-950e-48d7-b858-299fa0f55a53" />

```
import seaborn as sns
import numpy as np
import pandas as pd
np.random.seed(0)
marks = np.random.normal(loc=70, scale=10, size=100)
np.random.seed(1)
num_var = np.random.randn(1000)
num_var = pd.Series(num_var, name = "Numerical Variable")
num_var
```
<img width="525" height="248" alt="Screenshot 2025-10-16 233134" src="https://github.com/user-attachments/assets/85cbf9e1-a6f2-4e1f-bd26-d11a4e7f1054" />

```
plt.figure(figsize=(8, 5))
sns.histplot(num_var, kde=True, bins=30, color='skyblue')
plt.title('Histogram of Numerical Variable with KDE')
plt.xlabel('Numerical Variable')
plt.ylabel('Frequency')
plt.show()
```
<img width="846" height="531" alt="Screenshot 2025-10-16 233140" src="https://github.com/user-attachments/assets/e1213c31-54ff-416f-ab10-f59a0cf32d40" />

```
plt.figure(figsize=(8, 5))
sns.histplot(data=tit, x='pclass', hue='survived', kde=False, multiple='stack', palette='tab10')
plt.title('Passenger Class Distribution by Survival (Stacked Histogram)')
plt.xlabel('Passenger Class (1, 2, 3)')
plt.ylabel('Count')
plt.legend(title='Survived', labels=['Yes', 'No'])
plt.xticks(ticks=[1, 2, 3])
plt.show()
```
<img width="892" height="536" alt="Screenshot 2025-10-16 233145" src="https://github.com/user-attachments/assets/8dd8d116-6f74-4141-998d-8d7987ef00cb" />

# Result:
Thus the program to Perform Data Visualization using seaborn python library for the given datas is executed successfully.
