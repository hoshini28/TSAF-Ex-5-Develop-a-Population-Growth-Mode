# TSAF-Ex-5-Develop-a-Population-Growth-Mode

## AIM:
To develop a simple mathematical model for population growth using Python and use the
model to predict future population.


## PROGRAM:

```
import matplotlib.pyplot as plt
import numpy as np

# Decade-based temperature anomaly data (°C)
decade = np.array([1980, 1990, 2000, 2010, 2020])
temp_anomaly = np.array([0.26, 0.40, 0.54, 0.65, 0.85])

# Time steps (t = 0 to 4)
t = np.arange(len(decade))

# Polyfit linear estimation
rate, base_temp = np.polyfit(t, temp_anomaly, 1)

# Model estimations
fitted_temp = base_temp + rate * t
print(f"Base Anomaly (1980): {base_temp:.3f} °C")
print(f"Warming Rate per Decade: {rate:.3f} °C/decade")
print("\nDecade Actual (°C) Predicted (°C)")
for d, act, pred in zip(decade, temp_anomaly, fitted_temp):
 print(f"{d} {act:10.2f} {pred:14.3f}")

# Projections for 2030, 2040, 2050
future_decade = np.array([2030, 2040, 2050])
future_t = np.array([5, 6, 7])
future_temp = base_temp + rate * future_t
print("\nDecadal Temperature Anomaly Forecast:")
for fd, ft in zip(future_decade, future_temp):
 print(f"{fd}s: +{ft:.3f} °C")

# Plotting
plt.plot(decade, temp_anomaly, 'o-', label='Observed Anomaly')
plt.plot(decade, fitted_temp, 'x--', label='Trend Line')
plt.plot(future_decade, future_temp, 's:', label='Decadal Projection')
plt.title("Global Temperature Anomaly Model")
plt.xlabel("Decade")
plt.ylabel("Temperature Anomaly (°C)")
plt.legend()
plt.grid(True)
plt.show()

```

## OUTPUT:
<img width="530" height="512" alt="image" src="https://github.com/user-attachments/assets/128c5966-bb04-4d36-83f3-a82fe427baf7" />
