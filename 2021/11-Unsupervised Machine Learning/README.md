This section uses one CSV file. This data originates from [Fantasy Pros](https://www.fantasypros.com/nba/).

To use a csv use the `read_csv` method from pandas.
```python
import pandas as pd
```

In this section we use Fantasy Basketball 2021 Draft Rankings.
```python
df = pd.read_csv('https://raw.githubusercontent.com/fantasydatapros/LearnPythonWithBasketball/main/2021/11-Unsupervised%20Machine%20Learning/FantasyPros_2021_Overall_NBA_Rankings.csv')
```
