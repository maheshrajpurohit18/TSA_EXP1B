# Ex.No: 1B                     CONVERSION OF NON STATIONARY TO STATIONARY DATA
# Date: 

### AIM:
To perform regular differncing,seasonal adjustment and log transformatio on international airline passenger data
### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the data preprocessing if needed and apply regular differncing,seasonal adjustment,log transformation.
4. Plot the data according to need, before and after regular differncing,seasonal adjustment,log transformation.
5. Display the overall results.
### PROGRAM:
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
```
```
data=pd.read_csv("C:/Users/SEC/Downloads/archive/data_date.csv")
```
```
x=data['Date']
y=data['AQI Value']
plt.xlabel('Date')
plt.ylabel('AQI Value')
plt.plot(x,y)
```
```
data3=data
data3['diff']=data3['AQI Value'].diff()
data3=data3.dropna()
x=data3['Date']
y=data3['AQI Value']
plt.xlabel('Date')
plt.ylabel('AQI Value')
plt.plot(x,y)
```
```
data1=data
data1['SeasonalAdjustment'] = data1['AQI Value'].rolling(window=12).mean()
data1['SeasonalAdjustment'].dropna()
x=data1['Date']
y=data1["SeasonalAdjustment"]
plt.xlabel('Date')
plt.ylabel('AQI Value')
plt.plot(x,y)
```
```
data2=data
data2['log']=np.log(data2['diff']).dropna()
data2=data2.dropna()
x=data2['Date']
y=data2['log']
plt.xlabel('Date')
plt.ylabel('AQI Value')
# plt.figure(figsize=(8, 6))
plt.plot(x,y)
```

### OUTPUT:


REGULAR DIFFERENCING:
![image](https://github.com/user-attachments/assets/1f6c05c0-a960-49f3-a233-494c838596ca)


SEASONAL ADJUSTMENT:
![image](https://github.com/user-attachments/assets/a246f233-78ad-4f14-ab77-3c6ace41032d)


LOG TRANSFORMATION:
![image](https://github.com/user-attachments/assets/485f8bac-6102-45fd-a68d-55ab95f6c1ba)



### RESULT:
Thus we have created the python code for the conversion of non stationary to stationary data on international airline passenger
data.
