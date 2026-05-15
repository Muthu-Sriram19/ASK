# ASK & FSK
# Aim
Write a simple Python program for the modulation and demodulation of ASK and FSK.
# Tools required

* Google colab
# Program
## ASK
```
import numpy as np
import matplotlib.pyplot as plt

# Time and message
t = np.linspace(0, 1, 1000)
bits = [1,0,1,1,0]
msg = np.repeat(bits, 200)

# Carrier and ASK
carrier = np.sin(2*np.pi*50*t)
ask = msg * carrier

# Plot
plt.figure(figsize=(8,5))

plt.subplot(3,1,1)
plt.plot(msg)
plt.title("Message")

plt.subplot(3,1,2)
plt.plot(carrier)
plt.title("Carrier")

plt.subplot(3,1,3)
plt.plot(ask)
plt.title("ASK Signal")

plt.tight_layout()
plt.show()
```
## FSK
```
import numpy as np
import matplotlib.pyplot as plt

# Binary data
bits = [1,0,1,1,0]
msg = np.repeat(bits, 100)

# Time
t = np.linspace(0, 1, len(msg))

# FSK Modulation
fsk = np.sin(2*np.pi*(30 + 40*msg)*t)

# Plot
plt.figure(figsize=(8,4))

plt.subplot(2,1,1)
plt.plot(msg)
plt.title("Message Signal")

plt.subplot(2,1,2)
plt.plot(fsk)
plt.title("FSK Signal")

plt.tight_layout()
plt.show()
```
# Output Waveform

## ASK
<img width="1190" height="790" alt="ask" src="https://github.com/user-attachments/assets/f5530c0e-4e48-4369-8ac4-56ebb12298c5" />

## FSK
<img width="1201" height="1012" alt="fsk" src="https://github.com/user-attachments/assets/dbd1e225-19c7-4ee9-a7a5-07570ec9fc1a" />

# Results
Thus, the ASK and FSK performed using colab
