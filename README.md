``` python
from requests import Request, Session
from requests.exceptions import ConnectionError, Timeout, TooManyRedirects
import json

```
``` python
url = 'https://pro-api.coinmarketcap.com/v1/cryptocurrency/listings/latest' 
#Original Sandbox Environment: 'https://sandbox-api.coinmarketcap.com/v1/cryptocurrency/listings/latest'
parameters = {
  'start':'1',
  'limit':'15',
  'convert':'USD'
}
headers = {
  'Accepts': 'application/json',
  'X-CMC_PRO_API_KEY': '0ad53085-1cb2-4eb8-ad9e-3ffbd7e56509',
}

session = Session()
session.headers.update(headers)

try:
  response = session.get(url, params=parameters)
  data = json.loads(response.text)
  #print(data)
except (ConnectionError, Timeout, TooManyRedirects) as e:
  print(e)

import pandas as pd

pd.set_option('display.max_columns', None)
pd.set_option('display.max_rows', None)

def api_runner():
    global df
    url = 'https://pro-api.coinmarketcap.com/v1/cryptocurrency/listings/late

 parameters = {
      'start':'1',
      'limit':'15',
      'convert':'USD'
    }
headers = {
      'Accepts':'application/json',
      'X-CMC_PRO_API_KEY':'0ad53085-1cb2-4eb8-ad9e-3ffbd7e5650'
   }
session = Session()
session.headers.update(headers)

try:
    response = session.get(url, params=parameters)
    data = json.loads(response.text)
except(ConnectionError, Timeout, TooManyDirects) as e:
    print(e)

df2 = pd.json_normalize(data)
df2['Timestamp'] = pd.to_datetime('now')
df_append = pd.DataFrame(df2)
df = pd.concat([df2,df_append])

import os 
from time import time
from time import sleep

for i in range(333):
    api_runner()
    print('API Runner completed')
    sleep(60) #sleep for 1 minute
exit()

df72 = pd.read_csv(r'C:\Users\subomi\Documents\Python Scripts\API.csv')
df72

df

df3 = df.groupby('name', sort=False)[['quote.USD.percent_change_1h','quote.USD.percent_change_24h','quote.USD.percent_change_7d','quote.USD.percent_change_30d','quote.USD.percent_change_60d','quote.USD.percent_change_90d']].mean()
df3

df4 = df3.stack()
df4

df5 = df4.to_frame(name='values')
df5

df5.count()

index = pd.Index(range(90))

df6 = df5.set_index(index)
df6

df7 = df6.rename(columns={'level_1': 'percent_change'})
df7

df7['percent_change'] = df7['percent_change'].replace(['quote.USD.percent_change_24h','quote.USD.percent_change_7d','quote.USD.percent_change_30d','quote.USD.percent_change_60d','quote.USD.percent_change_90d'],['24h','7d','30d','60d','90d'])
df7

import seaborn as sns
import matplotlib.pyplot as plt

sns.catplot(x='percent_change', y='values', hue='name', data=df7, kind='point')

df10 = df[['name','quote.USD.price','timestamp']]
df10 = df10.query("name == 'Bitcoin'")
df10
sns.set_theme(style="darkgrid")

sns.lineplot(x='timestamp', y='quote.USD.price', data = df10)

```


