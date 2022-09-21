This section uses [nba_api](https://github.com/swar/nba_api). I will give a short explaination of how to use each method. Linked is nba_api's documentation.

To use nba_api first install and import it.

```python
pip install nba_api
import nba_api
```
In this section we use 2021 [player game logs](https://github.com/swar/nba_api/blob/master/docs/nba_api/stats/endpoints/playergamelogs.md), which is individual game stats for individual players. Again, don't worry too much about the specifics of the code since things like json is outside the scope of the course, but if interested you can follow up for more information on the nba_api github.
```python
from nba_api.stats.endpoints import playergamelogs

response = playergamelogs.PlayerGameLogs(season_nullable='2021-22')
content = json.loads(response.get_json())
results = content['resultSets'][0]
headers = results['headers']
rows = results['rowSet']
df = pd.DataFrame(rows,columns= headers)
```
- season_nullable: the year you want to pull data for (string: 'YYYY-YY')
