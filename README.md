# Data Analysis in Python with pandas

##import pandas

```python
import pandas as pd
```

See more about pandas:

>[Python Data Analysis Library](http://pandas.pydata.org/)

and

>[Tutorials](http://pandas.pydata.org/pandas-docs/version/0.15.2/tutorials.html)


##1.Create a table for content

There is a easy way to show the information crawled from web content which has to be declared to data frame of pandas

```python
df = pd.DataFrame(Your List)
```

##2.Main topic in this example

###Use urls to get yahoo movie reviews

```python
import requests
from bs4 import BeautifulSoup as bs 
```

###Generate the DataFrame

```python
import pandas as pd
df = pd.DataFrame(commentList)
```

###Clear dirty data  ex:\n

There are some dirty data will affect the preprocessing. 

```python
df['Comment'] =df['Comment'].map(lambda x: ''.join(x.split()))
df['Title'] =df['Title'].map(lambda x: ''.join(x.split()))
df['Date'] =df['Date'].map(lambda x: ''.join(x.split('2016-')))
```

###Choose and sort DataFrame

```python
starPlot =  df.ix[0:, ['Date','Star']]
starPlot = starPlot.sort(['Date','Star'], ascending=[1, 0])
```

###Use "Group by" to get Average star with Date

```python
grouped = df.groupby(['Date'], as_index=False).mean()
```

###Plot and Output figure

See compeletly example in [DataAnalysis2-in-Python-with-panda](https://github.com/ChiLunHuang/DataAnalysis2-in-Python-with-panda/blob/master/Data%20Analysis%202%20in%20Python%20with%20pandas.ipynb) 





