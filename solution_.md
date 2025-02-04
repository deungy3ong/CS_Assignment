import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv('istherecorrelation.csv', delimiter=';')

fig, ax1 = plt.subplots(figsize=(8, 6), dpi=300)

color = 'tab:blue'
ax1.set_xlabel('Year')
ax1.set_ylabel('WO[X1000]', color=color)
ax1.plot(data['Year'], data['WO [x1000]'], color=color)
ax1.tick_params(axis='y', labelcolor=color)

ax2 = ax1.twinx()
color = 'tab:green'
ax2.set_ylabel('NL Beer Consumption [x1000 hectoliter]', color=color)
ax2.plot(data['Year'], data['NL Beer consumption [x1000 hectoliter]'], color=color)
ax2.tick_params(axis='y', labelcolor=color)

plt.title('Correlation Between WO, NL Beer Consumption and year')

plt.savefig('wo&beer_plot.png')

plt.show()
![](wo&beer_plot.png)
· Between 2006 and 2018, the 'WO' showed a steady increase. However, 'NL Beer consumption' experienced fluctuations from 2006 to 2012, followed by a rapid growth thereafter.
