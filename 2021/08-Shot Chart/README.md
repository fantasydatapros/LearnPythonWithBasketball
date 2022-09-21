This section uses two CSV files. This data originates from [Lahman's Baseball Database](https://www.seanlahman.com/baseball-archive/statistics/).

To use a csv use the `read_csv` method from pandas.
```python
import pandas as pd
```

In this section we use salary data from 1985 up to 2016.
```python
salaries = pd.read_csv('https://raw.githubusercontent.com/fantasydatapros/LearnPythonWithBaseball/main/2021/08-Analyzing%20MLB%20Salary%20Data/Salaries.csv')
```

We also use teams data for win totals.
```python
teams = pd.read_csv('https://raw.githubusercontent.com/fantasydatapros/LearnPythonWithBaseball/main/2021/08-Analyzing%20MLB%20Salary%20Data/Teams.csv')
```

