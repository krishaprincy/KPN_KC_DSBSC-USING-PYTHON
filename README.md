# DSBSC-using-Python

Aim

To implement and analyze Double Sideband Suppressed Carrier (DSB-SC) modulation using Python's NumPy and Matplotlib libraries.

Apparatus Required

1.	Software: Python with NumPy and Matplotlib libraries
2.	Hardware: Personal Computer
  
Theory

Double Sideband Suppressed Carrier (DSB-SC) modulation is a type of amplitude modulation where the carrier signal is suppressed, and only the sidebands (which contain the actual information) are transmitted.
The amplitude of the carrier wave is varied in accordance with the message signal, but unlike conventional AM, the carrier component is not transmitted, making the transmission more power-efficient.


Algorithm


1.Initialize Parameters: Set the values for carrier frequency, message frequency, and sampling frequency.

2.Generate Time Axis: Create a time vector for the signal duration.

3.Generate Message Signal: Define the message signal as a cosine wave.

4.Generate Carrier Signal: Define the carrier signal as a cosine wave.

5.Generate DSB-SC Signal: Multiply the message signal and carrier signal to obtain the DSB-SC modulated signal.

6.Plot the Signals: Use Matplotlib to plot the message signal, carrier signal, and modulated signal.


Program
```
import numpy as np
import matplotlib.pyplot as plt

Am = 2.7
fm = 164
Ac = 5.4
fc = 1640
fs = 16400

t = np.arange(0, 2/fm, 1/fs)
m = Am * np.cos(2 * np.pi * fm * t)
plt.subplot(3, 1, 1)
plt.plot(t, m)
c = Ac * np.cos(2 * np.pi * fc * t)
plt.subplot(3, 1, 2)
plt.plot(t, c)
s1 = (Ac + m) * np.cos(2 * np.pi * fc * t)
s2 = (Ac - m) * np.cos(2 * np.pi * fc * t)
s = s1 - s2
plt.subplot(3, 1, 3)
plt.plot(t, s)

```

Output Waveform

<img width="1257" height="883" alt="image" src="https://github.com/user-attachments/assets/d0184504-e313-4452-af84-e156450bf3a4" />



Tabular Column

![WhatsApp Image 2025-12-04 at 15 38 34_07a5f5bd](https://github.com/user-attachments/assets/413eea53-e451-479c-95c3-f414dd97026f)



Result

The message signal, carrier signal, and DSB-SC modulated signal will be displayed in separate plots.
The modulated signal will contain two sidebands without the carrier component, representing the double sideband suppressed carrier waveform.
