This section uses [pybaseball](https://github.com/jldbc/pybaseball#readme). I will give a short explaination of how to use each method. Linked is pybaseball's documentation.

To use pybaseball first install and import it.

```python
pip install pybaseball
import pybaseball as pyb
```
In this section we use 2021 [batting_stats](https://github.com/jldbc/pybaseball/blob/master/docs/batting_stats.md), which is full year batting stats for qualifying players.
```python
pyb.batting_stats(2021, qual = 0)
```
- year: first argument is the year (int)
- qual: second argument is minimum number of at bats for a player to qualify (int)

We also use 2021 [standings](https://github.com/jldbc/pybaseball/blob/master/docs/standings.md) data.
```python
pyb.standings(2021)
```
- year: first argument is the year (int)
