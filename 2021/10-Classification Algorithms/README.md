This section uses [nba_api](https://github.com/swar/nba_api) and one CSV. I will give a short explaination of how to use each method. Linked is nba_api's documentation.

To use a csv use the `read_csv` method from pandas.
```python
import pandas as pd
```

In this section the CSV we use contains MVP voting data from 1980 - 2017.
```python
df = pd.read_csv('https://raw.githubusercontent.com/fantasydatapros/LearnPythonWithBasketball/main/2021/10-Classification%20Algorithms/mvp_votings.csv')
```

For each of the seasons we have MVP data for we need to also pull season total stats. We do this through the nba_api. To use nba_api first install and import it.

```python
pip install nba_api
import nba_api
```
Specifically, we use [season totals](https://github.com/swar/nba_api/blob/master/docs/nba_api/stats/endpoints/leagueleaders.md) from 1980 - 2017  data, which is season long totals for each player every year. We can get this data one year at a time, to compile it for the entire data range we must use a for loop.
```python
from nba_api.stats import endpoints

for i in seasons:
    temp = endpoints.leagueleaders.LeagueLeaders(league_id = '00',
                                                per_mode48 = 'Totals',
                                                scope = 'S',
                                                season = i,
                                                season_type_all_star = 'Regular Season').league_leaders.get_data_frame()
    temp['season'] = i
    data = pd.concat([data, temp])
```
- league_id: league type the user desires to query, '00' refers to NBA but there are also g_league and wnba options.
- per_mode48: allows user to specify if they want season totals or per game averages
- scope: allows user to query rookies. We use 'S' to refer to the entire player database
- season: the year you want to pull data for (string: 'YYYY-YY')
- season_type_all_star: season type refers to if user wants data for `Regular Season`, `Pre Season`, `Playoffs`, or `All Star`
