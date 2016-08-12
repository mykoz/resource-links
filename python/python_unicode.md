
```python
# Convert from:  'If you\'re driving into town  With a dark'
# Convert to:  'If you're driving into town  With a dark'
import unicodedata
unicodedata.normalize('NFKD',"you\'re").encode('ascii', 'ignore'))
```


---

```
from __future__ import unicode_literals
```

```
import json
from datetime import datetime


filename = "tweets.json"


tweet_info = []
linect = -1
maxlines = 4132406 + 1
#maxlines = 10000

#with open('tw3.json', encoding='utf-8') as f:
with open(path_data+filename, encoding='utf-8') as f:
    for line in f:
        linect += 1
        if linect < maxlines:
            #print('\n')
            #print(linect, repr(line))
            d = json.loads(line)
            #print(type(d))
            #print(d)
            tw_date = d['created_at']    # d is of type dictionary
            #print(tw_date)
            tw_date= datetime.strptime(tw_date,'%a %b %d %H:%M:%S +0000 %Y')
            #tw_date= datetime.strptime(tw_date,'%a %b %d 00:00:00 +0000 %Y')
            tw_date = datetime.date(tw_date)
            tw_date_str = tw_date.strftime('%Y-%m-%d')
            #print(test)
            #print(type(tw_date))
            #tweet_info.append(tw_date)
            tweet_info.append(tw_date_str)
            
```
