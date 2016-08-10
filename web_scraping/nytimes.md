from Sunne:  


for anyone who wants to use the NYTimes API, here’s my code
```
import requests
import json
from datetime import datetime

url_list = []
date_list = []
for i in range(1,130):
    params = {'api-key':"###########", 'q': "query topic", 'begin_date': 20140610, 'page':_}
    params['page'] = i
    url = requests.get('https://api.nytimes.com/svc/search/v2/articlesearch.json', params=params)
    data = json.loads(url.text)
    for t in range(9):
        url_list1.append(data['response']['docs'][t]['web_url'])
        date_list1.append(datetime.strptime(data['response']['docs'][t]['pub_date'][:10], '%Y-%m-%d'))

#if you have python3 then the Article package works well.
#it grabs the full article from the html

from newspaper import Article

def parse_article(urls):
    for url in urls:
        url = Article(url, langauge='en')
        url.download()
        url.parse()
        print(url.text)
```  
