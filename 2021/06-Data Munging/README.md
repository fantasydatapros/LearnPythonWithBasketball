This section uses [nba_api](https://github.com/swar/nba_api). I will give a short explaination of how to use each method. Linked is nba_api's documentation.

To use nba_api first install and import it.

```python
pip install nba_api
import nba_api
```
In this section we use 2021 [season totals](https://github.com/swar/nba_api/blob/master/docs/nba_api/stats/endpoints/leagueleaders.md), which is full year stats for qualifying players. Nba_api calls this `LeagueLeaders`
```python
from nba_api.stats import endpoints
data = endpoints.leagueleaders.LeagueLeaders(season = '2021-22').league_leaders.get_data_frame()
```
- season: the year you want to pull data for (string: 'YYYY-YY')

We also use 2021 [Team Game Log](https://github.com/swar/nba_api/tree/master/nba_api) data which is used to aquire team records. Some of nba_api needs some extra code to pull everything properly, don't get too bogged down if youre confused by it. If you're interested you can read more on the team game log link.
```python
import json
response = endpoints.teamgamelogs.TeamGameLogs(season_nullable = '2021-22')
content = json.loads(response.get_json())
results = content['resultSets'][0]
headers = results['headers']
rows = results['rowSet']
record = pd.DataFrame(rows,columns= headers)
```
- season_nullable: the year you want to pull data for (string: 'YYYY-YY')
