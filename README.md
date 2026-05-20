# Ex.No: 05  IMPLEMENTATION OF TIME SERIES ANALYSIS AND DECOMPOSITION
### Date: 20/05/2026
### NAME : SANJAY C
### REG NO : 212223240150

### AIM:
To Illustrates how to perform time series analysis and decomposition on the monthly average temperature of a city/country and for airline passengers.

### REQUIREMENTS:
```
1.DATASET : APPLE STOCK PRICE
2.TECHNOLOGY USED : GOOGLE COLLAB
```

### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the decomposition process for the required data.
4. Plot the data according to need, either seasonal_decomposition or trend plot.
5. Display the overall results.

### PROGRAM:
```py
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose

apple_df = pd.read_csv('/content/apple.csv')

apple_df['Date'] = pd.to_datetime(apple_df['Date'])
apple_df.set_index('Date', inplace=True)

decomposition = seasonal_decompose(apple_df['Volume'], model='additive', period=3)

# Original Data
plt.figure(figsize=(12, 4))
plt.plot(apple_df['Volume'], label='Original Volume', color='blue')
plt.legend(loc='upper left')
plt.title('Original Data (Apple Stock Volume)')
plt.grid(True)
plt.show()

# Trend Component
plt.figure(figsize=(12, 4))
plt.plot(decomposition.trend, label='Trend', color='orange')
plt.legend(loc='upper left')
plt.title('Trend Component')
plt.grid(True)
plt.show()

# Seasonal Component
plt.figure(figsize=(12, 4))
plt.plot(decomposition.seasonal, label='Seasonal', color='green')
plt.legend(loc='upper left')
plt.title('Seasonal Component')
plt.grid(True)
plt.show()

# Residual Component
plt.figure(figsize=(12, 4))
plt.plot(decomposition.resid, label='Residual', color='red')
plt.legend(loc='upper left')
plt.title('Residual Component')
plt.grid(True)
plt.show()
```
### OUTPUT:
FIRST FIVE ROWS:



PLOTTING THE DATA:


<img width="1139" height="425" alt="image" src="https://github.com/user-attachments/assets/779f96e7-3d45-47c2-af54-12f358cd1a0e" />


SEASONAL PLOT REPRESENTATION :



<img width="1191" height="429" alt="image" src="https://github.com/user-attachments/assets/a3edf5f0-920b-4ece-adf1-9676d4d9d83e" />



TREND PLOT REPRESENTATION :


<img width="1205" height="413" alt="image" src="https://github.com/user-attachments/assets/9a9b2b00-3142-42c2-9b0a-b6a98de1a3e6" />


RESIDUAL REPRESENTATION :

<img width="1166" height="411" alt="image" src="https://github.com/user-attachments/assets/90a926d3-fd43-45ab-aa6d-9cd904310100" />



### RESULT:
Thus we have created the python code for the time series analysis and decomposition.
