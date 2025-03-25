# Ideal Sampling

# Aim:

To study and implement the process of ideal sampling and observe the sampled waveform.

# Tools Required:

Python (for simulation)

Digital Storage Oscilloscope (for hardware verification)

Signal Generator

Low Pass Filter

Breadboard & Connecting Wires

# Program:

import numpy as np

import matplotlib.pyplot as plt

fs = 1000  
t = np.arange(0, 0.1, 1/fs)  
fm = 50  
x = np.sin(2 * np.pi * fm * t)  

Ts = 1 / (10 * fm)  
n = np.arange(0, 0.1, Ts)  
xs = np.sin(2 * np.pi * fm * n) 
plt.figure(figsize=(10, 5))


plt.subplot(2, 1, 1)
plt.plot(t, x, 'b', label="Original Signal", linewidth=1.5)
plt.stem(n, xs, 'r', markerfmt='ro', basefmt=" ", linefmt='r', label="Sampled Signal")
plt.title("Ideal Sampling")
plt.xlabel("Time (s)")
plt.ylabel("Amplitude")
plt.legend()
plt.grid()


plt.subplot(2, 1, 2)
plt.stem(n, xs, 'r', markerfmt='ro', basefmt=" ", linefmt='r')
plt.title("Sampled Signal")
plt.xlabel("Time (s)")
plt.ylabel("Amplitude")
plt.grid()

plt.tight_layout()
plt.show()

# Output

![Experiment 1](https://github.com/user-attachments/assets/226fdede-01e7-4f57-9b69-a7d8e1a08e17)


# Results:

The sampled signal retains the information of the original signal.

The spacing between samples is uniform, as defined by the sampling interval.

Proper reconstruction is possible using an ideal low-pass filter.
