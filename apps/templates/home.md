Welcome!
========

**2017-09-07:** This app has three URLs that relay annual, quarterly and monthly macroeconomic time series
from [mini-kep parser](https://github.com/epogrebnyak/mini-kep).


You can get this data with [pandas](http://pandas.pydata.org/pandas-docs/stable/install.html) using code below:

```python
import pandas as pd

URL = {'a': 'http://mini-kep.herokuapp.com/annual',
    'q': 'http://mini-kep.herokuapp.com/quarterly',
    'm': 'http://mini-kep.herokuapp.com/monthly'}

def read_csv(source):
    return pd.read_csv(source, converters={0: pd.to_datetime}, index_col=0)

dfa, dfq, dfm = (read_csv(URL[freq]) for freq in 'aqm')
```

More to follow!
