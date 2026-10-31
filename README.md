# Ex.No:04   FIT ARMA MODEL FOR TIME SERIES
# Date: 31/10/2026



### AIM:
To implement ARMA model in python.
### DATASET:
Electric Production
### ALGORITHM:
1. Import necessary libraries.
2. Set up matplotlib settings for figure size.
3. Define an ARMA(1,1) process with coefficients ar1 and ma1, and generate a sample of 1000 data points using the ArmaProcess class. Plot the generated time series and set the title and x-axis limits.
4. Display the autocorrelation and partial autocorrelation plots for the ARMA(1,1) process using plot_acf and plot_pacf.
5. Define an ARMA(2,2) process with coefficients ar2 and ma2, and generate a sample of 10000data points using the ArmaProcess class. Plot the generated time series and set the title and x-axis limits.
6. Display the autocorrelation and partial autocorrelation plots for the ARMA(2,2) process using plot_acf and plot_pacf.
### PROGRAM:
```python
# 1. Import necessary libraries
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.arima_process import ArmaProcess
from statsmodels.graphics.tsaplots import plot_acf, plot_pacf

# 2. Set up matplotlib settings for figure size
plt.rcParams['figure.figsize'] = (12, 5)

# 3. Define an ARMA(1,1) process
# In statsmodels, the zero-lag coefficient must be 1, and the signs of AR coefficients are reversed.
ar1 = np.array([1, -0.6])  # AR coefficient = 0.6
ma1 = np.array([1, 0.4])   # MA coefficient = 0.4

arma_11 = ArmaProcess(ar1, ma1)
sample_11 = arma_11.generate_sample(nsample=1000)

# Plot the generated time series
plt.figure()
plt.plot(sample_11, color='blue', alpha=0.7)
plt.title("Simulated ARMA(1,1) Process")
plt.xlim(0, 1000)
plt.grid(True, linestyle=':', alpha=0.6)
plt.show()

# 4. Display the autocorrelation and partial autocorrelation plots for the ARMA(1,1) process
fig, axes = plt.subplots(1, 2, figsize=(15, 5))
plot_acf(sample_11, ax=axes[0], title="ACF - ARMA(1,1)", lags=40)
plot_pacf(sample_11, ax=axes[1], title="PACF - ARMA(1,1)", lags=40)
plt.show()

# 5. Define an ARMA(2,2) process
ar2 = np.array([1, -0.5, 0.25])  # AR coefficients = 0.5, -0.25
ma2 = np.array([1, 0.6, 0.3])    # MA coefficients = 0.6, 0.3

arma_22 = ArmaProcess(ar2, ma2)
sample_22 = arma_22.generate_sample(nsample=10000)

# Plot the generated time series
plt.figure()
plt.plot(sample_22, color='green', alpha=0.7)
plt.title("Simulated ARMA(2,2) Process")
plt.xlim(0, 10000)
plt.grid(True, linestyle=':', alpha=0.6)
plt.show()

# 6. Display the autocorrelation and partial autocorrelation plots for the ARMA(2,2) process
fig, axes = plt.subplots(1, 2, figsize=(15, 5))
plot_acf(sample_22, ax=axes[0], title="ACF - ARMA(2,2)", lags=40)
plot_pacf(sample_22, ax=axes[1], title="PACF - ARMA(2,2)", lags=40)
plt.show()
```
### OUTPUT:
SIMULATED ARMA(1,1) PROCESS:
<img width="1242" height="456" alt="image" src="https://github.com/user-attachments/assets/b984c0b9-8e43-4a6b-8db5-471996ce56f1" />





Autocorrelation & Partial Autocorrelation:
<img width="1238" height="567" alt="image" src="https://github.com/user-attachments/assets/02bac085-7f48-49eb-a70d-ad67b787017e" />



SIMULATED ARMA(2,2) PROCESS:
<img width="1245" height="563" alt="image" src="https://github.com/user-attachments/assets/53bfe084-1d10-4ac3-b59e-bea888d6118a" />

Autocorrelation & Partial Autocorrelation

<img width="1250" height="455" alt="image" src="https://github.com/user-attachments/assets/930e08ad-c97d-4a38-b29e-4b6c07b27eaa" />




### RESULT:
Thus, a python program is created to fir ARMA Model successfully.
