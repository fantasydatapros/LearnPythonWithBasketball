This section uses [nba_api](https://github.com/swar/nba_api). I will give a short explaination of how to use each method. Linked is nba_api's documentation.

To use nba_api first install and import it.

```python
pip install nba_api
import nba_api
```
In this section we use 2021 [shot chart](https://github.com/swar/nba_api/tree/master/nba_api) data, which is data on every shot every player took in 2021.
```python
from nba_api.stats.endpoints import shotchartdetail

response = shotchartdetail.ShotChartDetail(team_id=0, player_id=0, season_nullable='2021-22', season_type_all_star='Regular Season', context_measure_simple = 'FGA')

content = json.loads(response.get_json())
results = content['resultSets'][0]
headers = results['headers']
rows = results['rowSet']
df = pd.DataFrame(rows,columns= headers)
```
- season_nullable: the year you want to pull data for (string: 'YYYY-YY')
- season_type_all_star: season type refers to if you want data for `Regular Season`, `Pre Season`, `Playoffs`, or `All Star`
- context_measure_simple: the type of play you want shot chart data for, we use all field goals attempted but you can also look at just field goals made or threes attempted. You can always filter after so I usually keep my initial search as broad as possible (unless there is so much data it starts becoming an issue).

Note: nba_api does not specify documentation on `team_id` and `player_id` but I assume these give you the option to search for specific teams or players. The 0 value that we use gives us data on all players and teams.

