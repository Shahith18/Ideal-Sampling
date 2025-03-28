# Ideal-Sampling

# Name : MOAHAMMED SHAHITH S
# Reg no : 212223060162
Aim:
    To simulate the process of sampling a continuous impulse signal and reconstructing it using the resampling method.
To visualize the differences between the original impulse signal, the sampled version, and the reconstructed signal.


Tools required:

Programming Language: Python

Libraries Used
NumPy for numerical computations
Matplotlib for plotting signals
SciPy (resample) for signal reconstruction
Computer with Python installed or an online Python environment (e.g., Jupyter Notebook, Google Colab)


Program:
import numpy as np
import matplotlib.pyplot as plt
from scipy.signal import resample

# Sampling frequency and time vector
fs = 200
t = np.arange(0, 1, 1/fs) 
f = 8

# Continuous signal
signal = np.sin(2 * np.pi * f * t)

# Plot continuous signal
plt.figure(figsize=(10, 4))
plt.plot(t, signal, label='Continuous Signal')
plt.title('Continuous Signal (fs = 200 Hz)')  # Corrected title
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.legend()
plt.show()

# Sampled signal
t_sampled = np.arange(0, 1, 1/fs)
signal_sampled = np.sin(2 * np.pi * f * t_sampled)

# Plot sampled signal
plt.figure(figsize=(10, 4))
plt.plot(t, signal, label='Continuous Signal', alpha=0.7)
plt.stem(t_sampled, signal_sampled, linefmt='r-', markerfmt='ro', basefmt='r-', label='Sampled Signal (fs = 200 Hz)')  # Corrected label
plt.title('Sampling of Continuous Signal (fs = 200 Hz)')  # Corrected title
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.legend()
plt.show()

# Reconstructing the signal
reconstructed_signal = resample(signal_sampled, len(t))

# Plot reconstructed signal
plt.figure(figsize=(10, 4))
plt.plot(t, signal, label='Continuous Signal', alpha=0.7)
plt.plot(t, reconstructed_signal, 'r--', label='Reconstructed Signal (fs = 200 Hz)')  # Corrected label
plt.title('Reconstruction of Sampled Signal (fs = 200 Hz)')  # Corrected title
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.legend()
plt.show()



Output Waveform:

![continuos signal](https://github.com/user-attachments/assets/d2495de1-f581-4317-bc79-2d6eee80b4dc)
![sampling of continuous signal](https://github.com/user-attachments/assets/d4311e93-8c25-4ebc-b916-562a1293a862)
![Reconstruction of sampled signal](https://github.com/user-attachments/assets/5ba83a3d-875d-4a10-a252-96a3ef112aad)



Results:

The original continuous impulse signal is displayed.
The sampled impulse signal appears as discrete spikes at sampled time intervals.
The reconstructed impulse signal approximates the original impulse, showing how sampling and reconstruction affect sharp signals.
