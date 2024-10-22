---
title: yfinance
date: 2024-10-22T12:22:03+08:00
draft: False
featuredImage: https://images.unsplash.com/photo-1727968913595-a51828d7cf54?ixid=M3w0NjAwMjJ8MHwxfHJhbmRvbXx8fHx8fHx8fDE3Mjk1NzA4MTh8&ixlib=rb-4.0.3
featuredImagePreview: https://images.unsplash.com/photo-1727968913595-a51828d7cf54?ixid=M3w0NjAwMjJ8MHwxfHJhbmRvbXx8fHx8fHx8fDE3Mjk1NzA4MTh8&ixlib=rb-4.0.3
---

# [ranaroussi/yfinance](https://github.com/ranaroussi/yfinance)

# Download market data from Yahoo! Finance's API

<table border=1 cellpadding=10><tr><td>

#### \*\*\* IMPORTANT LEGAL DISCLAIMER \*\*\*

---

**Yahoo!, Y!Finance, and Yahoo! finance are registered trademarks of
Yahoo, Inc.**

yfinance is **not** affiliated, endorsed, or vetted by Yahoo, Inc. It's
an open-source tool that uses Yahoo's publicly available APIs, and is
intended for research and educational purposes.

**You should refer to Yahoo!'s terms of use**
([here](https://policies.yahoo.com/us/en/yahoo/terms/product-atos/apiforydn/index.htm),
[here](https://legal.yahoo.com/us/en/yahoo/terms/otos/index.html), and
[here](https://policies.yahoo.com/us/en/yahoo/terms/index.htm)) **for
details on your rights to use the actual data downloaded. Remember - the
Yahoo! finance API is intended for personal use only.**

</td></tr></table>

---

<a target="new" href="https://pypi.python.org/pypi/yfinance"><img border=0 src="https://img.shields.io/badge/python-2.7,%203.6+-blue.svg?style=flat" alt="Python version"></a>
<a target="new" href="https://pypi.python.org/pypi/yfinance"><img border=0 src="https://img.shields.io/pypi/v/yfinance.svg?maxAge=60%" alt="PyPi version"></a>
<a target="new" href="https://pypi.python.org/pypi/yfinance"><img border=0 src="https://img.shields.io/pypi/status/yfinance.svg?maxAge=60" alt="PyPi status"></a>
<a target="new" href="https://pypi.python.org/pypi/yfinance"><img border=0 src="https://img.shields.io/pypi/dm/yfinance.svg?maxAge=2592000&label=installs&color=%2327B1FF" alt="PyPi downloads"></a>
<a target="new" href="https://www.codefactor.io/repository/github/ranaroussi/yfinance"><img border=0 src="https://www.codefactor.io/repository/github/ranaroussi/yfinance/badge" alt="CodeFactor"></a>
<a target="new" href="https://github.com/ranaroussi/yfinance"><img border=0 src="https://img.shields.io/github/stars/ranaroussi/yfinance.svg?style=social&label=Star&maxAge=60" alt="Star this repo"></a>
<a target="new" href="https://twitter.com/aroussi"><img border=0 src="https://img.shields.io/twitter/follow/aroussi.svg?style=social&label=Follow&maxAge=60" alt="Follow me on twitter"></a>


**yfinance** offers a threaded and Pythonic way to download market data from [Yahoo!Ⓡ finance](https://finance.yahoo.com).

→ Check out this [Blog post](https://aroussi.com/#post/python-yahoo-finance) for a detailed tutorial with code examples.

[Changelog »](https://github.com/ranaroussi/yfinance/blob/main/CHANGELOG.rst)

---

- [Installation](#installation)
- [Quick start](#quick-start)
- [Advanced](#logging)
- [Wiki](https://github.com/ranaroussi/yfinance/wiki)
- [Contribute](#developers-want-to-contribute)

---

## Installation

Install `yfinance` using `pip`:

``` {.sourceCode .bash}
$ pip install yfinance --upgrade --no-cache-dir
```

[With Conda](https://anaconda.org/ranaroussi/yfinance).

To install with optional dependencies, replace `optional` with: `nospam` for [caching-requests](#smarter-scraping), `repair` for [price repair](https://github.com/ranaroussi/yfinance/wiki/Price-repair), or `nospam,repair` for both:

``` {.sourceCode .bash}
$ pip install "yfinance[optional]"
```

[Required dependencies](./requirements.txt) , [all dependencies](./setup.py#L62).

---

## Quick Start

### The Ticker module

The `Ticker` module, which allows you to access ticker data in a more Pythonic way:

```python
import yfinance as yf

msft = yf.Ticker("MSFT")

# get all stock info
msft.info

# get historical market data
hist = msft.history(period="1mo")

# show meta information about the history (requires history() to be called first)
msft.history_metadata

# show actions (dividends, splits, capital gains)
msft.actions
msft.dividends
msft.splits
msft.capital_gains  # only for mutual funds & etfs

# show share count
msft.get_shares_full(start="2022-01-01", end=None)

# show financials:
msft.calendar
msft.sec_filings
# - income statement
msft.income_stmt
msft.quarterly_income_stmt
# - balance sheet
msft.balance_sheet
msft.quarterly_balance_sheet
# - cash flow statement
msft.cashflow
msft.quarterly_cashflow
# see `Ticker.get_income_stmt()` for more options

# show holders
msft.major_holders
msft.institutional_holders
msft.mutualfund_holders
msft.insider_transactions
msft.insider_purchases
msft.insider_roster_holders

msft.sustainability

# show recommendations
msft.recommendations
msft.recommendations_summary
msft.upgrades_downgrades

# show analysts data
msft.analyst_price_targets
msft.earnings_estimate
msft.revenue_estimate
msft.earnings_history
msft.eps_trend
msft.eps_revisions
msft.growth_estimates

# Show future and historic earnings dates, returns at most next 4 quarters and last 8 quarters by default.
# Note: If more are needed use msft.get_earnings_dates(limit=XX) with increased limit argument.
msft.earnings_dates

# show ISIN code - *experimental*
# ISIN = International Securities Identification Number
msft.isin

# show options expirations
msft.options

# show news
msft.news

# get option chain for specific expiration
opt = msft.option_chain('YYYY-MM-DD')
# data available via: opt.calls, opt.puts
```

For tickers that are ETFs/Mutual Funds, `Ticker.funds_data` provides access to fund related data. 

Funds' Top Holdings and other data with category average is returned as `pd.DataFrame`.

```python
import yfinance as yf
spy = yf.Ticker('SPY')
data = spy.funds_data

# show fund description
data.description

# show operational information
data.fund_overview
data.fund_operations

# show holdings related information
data.asset_classes
data.top_holdings
data.equity_holdings
data.bond_holdings
data.bond_ratings
data.sector_weightings
```

If you want to use a proxy server for downloading data, use:

```python
import yfinance as yf

msft = yf.Ticker("MSFT")

msft.history(..., proxy="PROXY_SERVER")
msft.get_actions(proxy="PROXY_SERVER")
msft.get_dividends(proxy="PROXY_SERVER")
msft.get_splits(proxy="PROXY_SERVER")
msft.get_capital_gains(proxy="PROXY_SERVER")
msft.get_balance_sheet(proxy="PROXY_SERVER")
msft.get_cashflow(proxy="PROXY_SERVER")
msft.option_chain(..., proxy="PROXY_SERVER")
...
```

### Multiple tickers

To initialize multiple `Ticker` objects, use

```python
import yfinance as yf

tickers = yf.Tickers('msft aapl goog')

# access each ticker using (example)
tickers.tickers['MSFT'].info
tickers.tickers['AAPL'].history(period="1mo")
tickers.tickers['GOOG'].actions
```

To download price history into one table:

```python
import yfinance as yf
data = yf.download("SPY AAPL", period="1mo")
```

#### `yf.download()` and `Ticker.history()` have many options for configuring fetching and processing. [Review the Wiki](https://github.com/ranaroussi/yfinance/wiki) for more options and detail.

### Sector and Industry

The `Sector` and `Industry` modules allow you to access the US market information.

To initialize, use the relevant sector or industry key as below. (Complete mapping of the keys is available in `const.py`.)

```python
import yfinance as yf

tech = yf.Sector('technology')
software = yf.Industry('software-infrastructure')

# Common information
tech.key
tech.name
tech.symbol
tech.ticker
tech.overview
tech.top_companies
tech.research_reports

# Sector information
tech.top_etfs
tech.top_mutual_funds
tech.industries

# Industry information
software.sector_key
software.sector_name
software.top_performing_companies
software.top_growth_companies
```

The modules can be chained with Ticker as below.
```python
import yfinance as yf

# Ticker to Sector and Industry
msft = yf.Ticker('MSFT')
tech = yf.Sector(msft.info.get('sectorKey'))
software = yf.Industry(msft.info.get('industryKey'))

# Sector and Industry to Ticker
tech_ticker = tech.ticker
tech_ticker.info
software_ticker = software.ticker
software_ticker.history()
```

### Market Screener
The `Screener` module allows you to screen the market based on specified queries.

#### Query Construction
To create a query, you can use the `EquityQuery` class to construct your filters step by step. The queries support operators: `GT` (greater than), `LT` (less than), `BTWN` (between), `EQ` (equals), and logical operators `AND` and `OR` for combining multiple conditions.

#### Screener
The `Screener` class is used to execute the queries and return the filtered results. You can set a custom body for the screener or use predefined configurations.

<!-- TODO: link to Github Pages for more including list of predefined bodies, supported fields, operands, and sample code -->

### Logging

`yfinance` now uses the `logging` module to handle messages, default behaviour is only print errors. If debugging, use `yf.enable_debug_mode()` to switch logging to debug with custom formatting.

### Smarter scraping

Install the `nospam` packages for smarter scraping using `pip` (see [Installation](#installation)). These packages help cache calls such that Yahoo is not spammed with requests.

To use a custom `requests` session, pass a `session=` argument to
the Ticker constructor. This allows for caching calls to the API as well as a custom way to modify requests via  the `User-agent` header.

```python
import requests_cache
session = requests_cache.CachedSession('yfinance.cache')
session.headers['User-agent'] = 'my-program/1.0'
ticker = yf.Ticker('msft', session=session)
# The scraped response will be stored in the cache
ticker.actions
```

Combine `requests_cache` with rate-limiting to avoid triggering Yahoo's rate-limiter/blocker that can corrupt data.
```python
from requests import Session
from requests_cache import CacheMixin, SQLiteCache
from requests_ratelimiter import LimiterMixin, MemoryQueueBucket
from pyrate_limiter import Duration, RequestRate, Limiter
class CachedLimiterSession(CacheMixin, LimiterMixin, Session):
    pass

session = CachedLimiterSession(
    limiter=Limiter(RequestRate(2, Duration.SECOND*5)),  # max 2 requests per 5 seconds
    bucket_class=MemoryQueueBucket,
    backend=SQLiteCache("yfinance.cache"),
)
```

### Managing Multi-Level Columns

The following answer on Stack Overflow is for [How to deal with
multi-level column names downloaded with
yfinance?](https://stackoverflow.com/questions/63107801)

-   `yfinance` returns a `pandas.DataFrame` with multi-level column
    names, with a level for the ticker and a level for the stock price
    data
    -   The answer discusses:
        -   How to correctly read the the multi-level columns after
            saving the dataframe to a csv with `pandas.DataFrame.to_csv`
        -   How to download single or multiple tickers into a single
            dataframe with single level column names and a ticker column

### Persistent cache store

To reduce Yahoo, yfinance store some data locally: timezones to localize dates, and cookie. Cache location is:

- Windows = C:/Users/\<USER\>/AppData/Local/py-yfinance
- Linux = /home/\<USER\>/.cache/py-yfinance
- MacOS = /Users/\<USER\>/Library/Caches/py-yfinance

You can direct cache to use a different location with `set_tz_cache_location()`:

```python
import yfinance as yf
yf.set_tz_cache_location("custom/cache/location")
...
```

---

## Developers: want to contribute?

`yfinance` relies on community to investigate bugs and contribute code. Developer guide: https://github.com/ranaroussi/yfinance/discussions/1084

---

### Legal Stuff

**yfinance** is distributed under the **Apache Software License**. See
the [LICENSE.txt](./LICENSE.txt) file in the release for details.


AGAIN - yfinance is **not** affiliated, endorsed, or vetted by Yahoo, Inc. It's
an open-source tool that uses Yahoo's publicly available APIs, and is
intended for research and educational purposes. You should refer to Yahoo!'s terms of use
([here](https://policies.yahoo.com/us/en/yahoo/terms/product-atos/apiforydn/index.htm),
[here](https://legal.yahoo.com/us/en/yahoo/terms/otos/index.html), and
[here](https://policies.yahoo.com/us/en/yahoo/terms/index.htm)) for
details on your rights to use the actual data downloaded.

---

### P.S.

Please drop me an note with any feedback you have.

**Ran Aroussi**