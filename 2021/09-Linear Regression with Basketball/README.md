This section uses [nba_api](https://github.com/swar/nba_api). I will give a short explaination of how to use each method. Linked is nba_api's documentation.

To use nba_api first install and import it.

```python
pip install nba_api
import nba_api
```
In this section we use 20 years of [season totals](https://github.com/swar/nba_api/blob/master/docs/nba_api/stats/endpoints/leagueleaders.md) from 2000 - 2021  data, which is data on every shot every player took in 2021.
```python
from nba_api.stats import endpoints

# initialize seasons we want to pull for
seasons = np.arange(2000,2021)
seasons2 = np.arange(0,22)

# loop through the seasons and add each year of NBA season totals to our dataframe. Start by initializing the first season.
data = endpoints.leagueleaders.LeagueLeaders(season='1999-00').league_leaders.get_data_frame()
data['season_start'] = 1999

for i, v in enumerate(seasons):
    temp = endpoints.leagueleaders.LeagueLeaders(season='{0}-{1}'.format(v,str(seasons2[i]+1).zfill(2))).league_leaders.get_data_frame()
    temp['season_start'] = v
    data = data.append(temp)
```
- season: the year you want to pull data for (string: 'YYYY-YY')

