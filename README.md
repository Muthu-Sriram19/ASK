# ASK
# Aim
Write a simple Python program for the modulation and demodulation of ASK and FSK.
# Tools required
# Program
import numpy as np
import matplotlib.pyplot as plt
t = np.linspace(0, 0.1, 1000)
msg = np.sin(2 * np.pi * 20 * t)
step = 0.2
pcm = step * np.round(msg / step)
delta = 0.05
dm = [0]
for s in msg:
    if s > dm[-1]:
        dm.append(dm[-1] + delta)
    else:
        dm.append(dm[-1] - delta)
dm = np.array(dm[:-1])
plt.figure(figsize=(8,6))
plt.subplot(3,1,1)
plt.plot(t, msg)
plt.title("Analog Signal")
plt.grid()

plt.subplot(3,1,2)
plt.step(t, pcm)
plt.title("PCM Signal")
plt.grid()

plt.subplot(3,1,3)
plt.step(t, dm)
plt.title("Delta Modulation")
plt.grid()

plt.tight_layout()
plt.show()
# Output Waveform
<img width="1040" height="730" alt="image" src="https://github.com/user-attachments/assets/786c5bea-42ac-436f-8a49-50de5af0d907" />

# Results
```
Attach the output waveform
```
# Hardware experiment output waveform.
