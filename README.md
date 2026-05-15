# ASK
# Aim
Write a simple Python program for the modulation and demodulation of ASK and FSK.
# Tools required
# Program
```

import numpy as np
import matplotlib.pyplot as plt

# Parameters
fs = 1000
t = np.arange(0, 1, 1/fs)

# Binary data
bits = np.array([1,0,1,1,0])
msg = np.repeat(bits, 200)

# ASK
fc = 20
ask = msg * np.sin(2*np.pi*fc*t)

# FSK
fsk = np.concatenate([
    np.sin(2*np.pi*(40 if b else 10)*t[i*200:(i+1)*200])
    for i, b in enumerate(bits)
])

# Plot
plt.figure(figsize=(8,6))

plt.subplot(3,1,1)
plt.plot(msg)
plt.title("Message Signal")
plt.grid()

plt.subplot(3,1,2)
plt.plot(ask)
plt.title("ASK Signal")
plt.grid()

plt.subplot(3,1,3)
plt.plot(fsk)
plt.title("FSK Signal")
plt.grid()

plt.tight_layout()
plt.show()
```
# Output Waveform
```
<img width="1034" height="808" alt="image" src="https://github.com/user-attachments/assets/636a4f60-a181-4109-b303-d6d0f120bada" />

```
# Results
```
Attach the output waveform
```
# Hardware experiment output waveform.

