This section uses [pybaseball](https://github.com/jldbc/pybaseball#readme). I will give a short explaination of how to use each method. Linked below is pybaseball's documentation.

To use pybaseball first install and import it.

```python
pip install pybaseball
import pybaseball as pyb
```
In this section we use 2021 [batting_stats_range](https://github.com/jldbc/pybaseball/blob/master/docs/batting_stats_range.md), which is batting stats over a specified time range.
```python
pyb.batting_stats_range('2021-05-01','2021-10-03')
```
- start_dt: first argument is the start date formatted `YYYY-MM-DD` (str)
- end_dt: second argument is the end date formatted `YYYY-MM-DD` (you can leave it blank and it will give you data up until the present day) (str)

We also use 2021 [statcast](https://github.com/jldbc/pybaseball/blob/master/docs/statcast.md) data for its individual pitch statistics.
```python
pyb.statcast(start_dt='2021-09-22', end_dt='2021-09-23')
```
- start_dt: first argument is the start date formatted `YYYY-MM-DD` (str)
- end_dt: second argument is the end date formatted `YYYY-MM-DD` (you can leave it blank and it will give you data up until the present day) (str)
