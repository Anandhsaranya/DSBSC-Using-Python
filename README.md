# DSBSC-Using-Python

# Aim:

To implement and analyze Double Sideband Suppressed Carrier (DSB-SC) modulation using Python's NumPy and Matplotlib libraries.

#  Apparatus Required:

Software: Python with NumPy and Matplotlib libraries Hardware: Personal Computer

# Theory:

Double Sideband Suppressed Carrier (DSB-SC) modulation is a type of amplitude modulation where the carrier signal is suppressed, and only the sidebands containing the information are transmitted.

# Algorithm:

# Initialize Parameters: 

Set the values for carrier frequency, message frequency, sampling frequency, and amplitude levels.
Generate Time Axis: Create a time vector for the desired duration of the signal.
Generate Message Signal: Create the message signal using a cosine function. 
Generate Carrier Signal: Create the carrier signal using a cosine function. 
Perform Modulation: Multiply the message and carrier signals to obtain the DSB-SC modulated signal.
Plot the Signals: Use Matplotlib to display the message signal, carrier signal, and DSB-SC signal.

# Program:
```
import numpy as np
import matplotlib.pyplot as plt

Am = 3.2
fm = 214
Ac = 6.4
fc = 2140
fs = 21400

t = np.arange(0, 2/fm, 1/fs)

m1 = Am * np.cos(2 * np.pi * fm * t)
plt.subplot(4, 1, 1)
plt.plot(t, m1)

c1 = Ac * np.cos(2 * np.pi * fc * t)
plt.subplot(4, 1, 2)
plt.plot(t, c1)

m2 = Am * np.cos(1.57 - (2 * np.pi * fm * t))
c2 = Ac * np.cos(1.57 - (2 * np.pi * fc * t))

s1 = c1 * m1
s2 = c2 * m2
slsb = s1 + s2
plt.subplot(4, 1, 3)
plt.plot(t, slsb)

susb = s1 - s2
plt.subplot(4, 1, 4)
plt.plot(t, susb)
```
# Output Waveform:
<img width="1260" height="736" alt="Dsbsc using python" src="https://github.com/user-attachments/assets/6a120de8-bb74-43cb-9d5e-e9538c6044ca" />

# Tabular Column:
![7th table](https://github.com/user-attachments/assets/b19539d7-d305-4b74-8654-a1630d8f44b4)

# Result:
The message, carrier, and DSB-SC modulated signals are successfully generated and displayed using Python. Thus, DSB-SC modulation is implemented using NumPy and Matplotlib.
