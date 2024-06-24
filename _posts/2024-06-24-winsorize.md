---
title: Winsorize
date: 2024-04-25 17:47:12 +0100
toc: true
categories: [Mathematics, Algorithms]
tags: [statistics, winsorize, outliers]
math: false
---
# Winsorize

Data often contains outliers which skew the result of analysis. [Winsorize](https://en.wikipedia.org/wiki/Winsorizing) replaces these outliers by some specified values. Typically, values below Nth and above Mth [percentile](https://en.wikipedia.org/wiki/Percentile) are replaced by Nth and Mth percentile values.
Using the [winsorize](https://docs.scipy.org/doc/scipy-1.13.1/reference/generated/scipy.stats.mstats.winsorize.html) function from Scipy, we can compare the result of a winsorized data below:
![img-description](/assets/post_assets/2024-06-24-winsorize/bokeh_plot.png)
_Showing the result of a winsorized data_

As it is seen the highest and lowest outliers are replaced with the 10% highest and 20% lowest percentiles, however, the outlier in the near -2.2 is still there since this outlier does not fall within the 10% highest or 20% lowest outliers.

```python
import numpy as np
from scipy.stats.mstats import winsorize
import holoviews as hv
hv.extension('bokeh')

def fun(x):
    return np.exp(-x*x)

arr = np.linspace(-3, 3, 100)
data = fun(arr)

# Adding some outliers to the data
data[20] = data[20] + 0.2
for i in range(10):
    data[45+i]= data[45+i] + 0.2
for i in range(10):
    data[i]= data[i] - 0.2
    data[99-i]= data[99-i] - 0.2

winsorized_data = winsorize(data, limits = (0.2 , 0.1))
# Plots
p1 = hv.Points((arr, data)).opts(title = 'Data with outliers')
p2 = hv.Points((arr, winsorized_data)).opts(title='Winsorized data')
p1+p2
```
