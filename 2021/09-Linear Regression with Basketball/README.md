This section uses [pybaseball](https://github.com/jldbc/pybaseball#readme). I will give a short explaination of how to use each method. Linked below is pybaseball's documentation.

To use pybaseball first install and import it.

```python
pip install pybaseball
import pybaseball as pyb
```
We use 2010 - 2019 [batting_stats](https://github.com/jldbc/pybaseball/blob/master/docs/batting_stats.md). In the section we break this up to extract 2019 data as its own DataFrame.
```python
pyb.batting_stats(2010, 2019)
```
- start_dt: first argument is the start year (int)
- end_dt: second argument is the end year (int) (you can leave it blank and it will give you data up until the present day)
