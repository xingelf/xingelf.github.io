---
title: "pandas Dataredader"
date: 2021-09-19
draft: false
categories:
  - "Tech"
tags:
  - "Finance"
  - "Python"
#featured_image: "/images/programing.jpeg"
#featured_image: "/images/fred-nasdaq.png"
#featureimage: "/images/fred-nasdaq.png"
#thumbnail: "/images/fred-nasdaq.png"

---

# pandas Datareaderとは
オンライン上のデータをダウンロードするライブラリです。

https://pandas-datareader.readthedocs.io/en/latest/index.html

データソース一覧はこちらにあります。
APIキーの取得が必要なものもあります。
fredやstooqはAPIキー不要でデータが取得できます。


https://pandas-datareader.readthedocs.io/en/latest/remote_data.html

## Fred 経済データ
St.Louis連銀が提供するデータソースです。

https://fred.stlouisfed.org/

### Fred NASDAQの時系列グラフ
NASDAQの時系列グラフを作成します。200期間移動平均SMA200も表示してみましょう。
わずか10行程度で作成できます。

```Python
import pandas_datareader.data as pdr
import datetime as dt
import matplotlib.pyplot as plt

date_to = dt.date.today()
ticker_f = 'NASDAQ100'
df = pdr.DataReader(ticker_f, 'fred', '2015-01-01', date_to).dropna()
df['SMA200'] = df.rolling(window = 200).mean()
df.plot()
plt.show()
```

{{< figure src="/images/fred-nasdaq.png" class="center" >}}

### Fred 失業率 Unemployment Rateのグラフ

米国の月次失業率推移のグラフを見てみましょう。
Covid19/新型コロナウイルスのインパクトの大きさが理解できます。

```Python
import pandas_datareader.data as pdr
import datetime as dt
import matplotlib.pyplot as plt

date_to = dt.date.today()
ticker_f = 'UNRATE'
df = pdr.DataReader(ticker_f, 'fred', '2015-01-01', date_to).dropna()
df.plot()
plt.show()
```

{{< figure src="/images/unrate.png" class="center" >}}


## NASDAQ

NASDAQの銘柄を簡単に取得できます。ティッカーシンボルの確認が可能です。

```Python
from pandas_datareader.nasdaq_trader import get_nasdaq_symbols
symbols = get_nasdaq_symbols()
symbols.info()
symbols.head()
symbols[symbols.index=='MSFT']
```
