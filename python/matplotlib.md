# matplotlib

#### How to plot a function of two variables with matplotlib

{% embed url="https://glowingpython.blogspot.com/2012/01/how-to-plot-two-variable-functions-with.html" %}

{% embed url="https://stackoverflow.com/questions/51765184/how-to-3d-plot-function-of-2-variables" %}

#### Plotting Equations with Python

{% embed url="https://medium.com/future-vision/plotting-equations-in-python-d0edd9f088c8" %}

{% embed url="https://stackoverflow.com/questions/42281966/how-to-plot-vectors-in-python-using-matplotlib" %}

#### Рисуем графики двух функций

```python
import matplotlib.pyplot as plt
import numpy as np

n = np.linspace(1, 30)
plt.plot(n, 4 * n * np.log2(n), label='$4n\log_2(n)$')
plt.plot(n, n ** 2, label='$n^2$')
plt.legend()
plt.savefig('plot_nlogn_and_n2.png')
```

#### Сравниваем отношение двух графиков функций

Сравним f(n)=2n^2 +5n+3 и g(n) = n^2

```python
import matplotlib.pyplot as plt
import numpy as np

n = np.linspace(1, 100)
plt.plot(n, (2 * n ** 2 + 5 * n + 3) / (n ** 2))
plt.savefig('plot_two_squares_fraction.png')
```

