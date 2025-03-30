# Ex No: 01 - IDEAL SAMPLING

## Aim
To study and analyze ideal sampling(impulse sampling), where a continuous time
signal is sampled using an impulse train,and observe its effect in both time and
frequency domains.The experiment aims to verify the sampling theorem,analyse
spectral characteristics, and understand signal reconstruction.
## Tools Required
IDE python with scipy and numpy


## Program:
~~~
import numpy as np
import matplotlib.pyplot as plt
from scipy.signal import resample
fs = 100
t = np.arange(0, 1, 1/fs) 
f = 5
signal = np.sin(2 * np.pi * f * t)
plt.figure(figsize=(10, 4))
plt.plot(t, signal, label='Continuous Signal')
plt.title('Continuous Signal (fs = 100 Hz)')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.legend()
plt.show()
t_sampled = np.arange(0, 1, 1/fs)
signal_sampled = np.sin(2 * np.pi * f * t_sampled)
plt.figure(figsize=(10, 4))
plt.plot(t, signal, label='Continuous Signal', alpha=0.7)
plt.stem(t_sampled, signal_sampled, linefmt='r-', markerfmt='ro', basefmt='r-', label='Sampled Signal (fs = 100 Hz)')
plt.title('Sampling of Continuous Signal (fs = 100 Hz)')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.legend()
plt.show()
reconstructed_signal = resample(signal_sampled, len(t))
plt.figure(figsize=(10, 4))
plt.plot(t, signal, label='Continuous Signal', alpha=0.7)
plt.plot(t, reconstructed_signal, 'r--', label='Reconstructed Signal (fs = 100 Hz)')
plt.title('Reconstruction of Sampled Signal (fs = 100 Hz)')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.legend()
plt.show()
~~~
## Output Waveform:
![exp1](https://github.com/user-attachments/assets/12c51ea8-d9c8-4813-ac5e-6e9cccd0484c)
![exp12](https://github.com/user-attachments/assets/210f945d-0dcd-453b-843c-6e161d1c429e)
![exp13](https://github.com/user-attachments/assets/04f83107-258f-438f-a90e-73c18a21a740)

## Results:
The result of ideal sampling is a discrete time signal that retains all theinformation of the original continuous time signal is obtained and output isverified.













