This section uses [pybaseball](https://github.com/jldbc/pybaseball#readme). I will give a short explaination of how to use each method. Linked below is pybaseball's documentation.

To use pybaseball first install and import it.

```python
pip install pybaseball
import pybaseball as pyb
```

This section uses 2021 [statcast](https://github.com/jldbc/pybaseball/blob/master/docs/statcast.md) data for its individual pitch statistics.
```python
pitches = pyb.statcast('2021-06-01', '2021-07-01')
```
- start_dt: first argument is the start date formatted `YYYY-MM-DD` (str)
- end_dt: second argument is the end date formatted `YYYY-MM-DD` (you can leave it blank and it will give you data up until the present day) (str)
