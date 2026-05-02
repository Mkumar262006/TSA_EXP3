# Ex.No: 03   COMPUTE THE AUTO FUNCTION(ACF)
### Register No : 212223240082
### Name: Manoj kumar S
### Date:02-05-2026 

### AIM:
To Compute the AutoCorrelation Function (ACF) of the data for the first 35 lags to determine the model
type to fit the data.
### ALGORITHM:
1. Import the necessary packages
2. Find the mean, variance and then implement normalization for the data.
3. Implement the correlation using necessary logic and obtain the results
4. Store the results in an array
5. Represent the result in graphical representation as given below.
### PROGRAM:
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
from statsmodels.graphics.tsaplots import plot_acf

file_path = 'matches.csv'  
data = pd.read_csv(file_path)


data['date'] = pd.to_datetime(data['date'], dayfirst=True, format='mixed')


data.set_index('date', inplace=True)


series = data['win_by_runs']

series = series.fillna(0)


plt.figure(figsize=(10, 6))
plot_acf(series, lags=35, alpha=0.05)

plt.title('AutoCorrelation Function (ACF) - IPL Matches (win_by_runs)')
plt.xlabel('Lags')
plt.ylabel('ACF Value')
plt.grid(True)

plt.show()

### OUTPUT:

<img width="890" height="591" alt="Screenshot 2026-05-02 090149" src="https://github.com/user-attachments/assets/b5fcf970-69eb-433b-ab38-6e4e04fa80c6" />


### RESULT:
        Thus we have successfully implemented the auto correlation function in python.
