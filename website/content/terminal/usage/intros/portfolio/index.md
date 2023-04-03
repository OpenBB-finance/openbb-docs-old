---
title: Portfolio
keywords: [portfolio, attribution, optimization, pnl, benchmark, return, volatility, metrics, broker, integration, report, optimization, risk, benchmark, brokers]
description: The Portfolio menu, and its sub-menus, are dedicated to properly explaining and optimizing your own portfolio. With features to load your own orderbook (transactions) it is possible to compare your results to that of a benchmark. For example, you are able to load both your portfolio and a benchmark (load and bench), then have the option to look into the performance compared to the benchmark asking the question "What if I invested all my money in the benchmark instead?" (perf) as well as see a wide variety of statistics and metrics (rsharpe, distr, var and metric). Next to that, with these findings you can apply optimization techniques to your portfolio through the Portfolio Optimization menu.
---

The Portfolio menu, and its sub-menus, are dedicated to properly explaining and optimizing your own portfolio. With features to load your own orderbook (transactions) it is possible to compare your results to that of a <a href="https://www.investopedia.com/terms/b/benchmark.asp" target="_blank" rel="noreferrer noopener">benchmark</a>. For example, you are able to load both your portfolio and a benchmark (<a href="/terminal/reference/portfolio/load" target="_blank" rel="noreferrer noopener">load</a> and <a href="/terminal/reference/portfolio/bench" target="_blank" rel="noreferrer noopener">bench</a>), then have the option to look into the performance compared to the benchmark asking the question "_What if I invested all my money in the benchmark instead?_" (<a href="/terminal/reference/portfolio/perf" target="_blank" rel="noreferrer noopener">perf</a>) as well as see a wide variety of statistics and metrics (<a href="/terminal/reference/portfolio/rsharpe/" target="_blank" rel="noreferrer noopener">rsharpe</a>, <a href="/terminal/reference/portfolio/distr" target="_blank" rel="noreferrer noopener">distr</a>, <a href="/terminal/reference/portfolio/var" target="_blank" rel="noreferrer noopener">var</a>
and <a href="/terminal/reference/portfolio/metric" target="_blank" rel="noreferrer noopener">metric</a>). Next to that, with these findings you can apply optimization techniques to your portfolio through the <a href="/terminal/usage/intros/portfolio/po/" target="_blank" rel="noreferrer noopener">Portfolio Optimization menu</a>.

## How to use

The Portfolio menu is called upon by typing `portfolio` which opens the following menu:

<img width="800" alt="image" src="https://user-images.githubusercontent.com/46355364/218995675-f09d21bc-9e64-4546-83d0-ce21e10b3b62.png"></img>

The first step in using this menu is loading a portfolio with <a href="/terminal/reference/portfolio/load" target="_blank" rel="noreferrer noopener">load</a>. Within this guide, we provide an example file when running `load --example` which will be used to explain the functionality through the guide. 

:::note If you wish to load in your own Excel holdings file, please follow the following steps:
1. Download the Excel file that can be used as a template [here](https://www.dropbox.com/s/03wjjf1lfkqjmtn/holdings_example.xlsx?dl=0).
2. Move the file inside the `portfolio/holdings` folder within the [OpenBBUserData](https://docs.openbb.co/terminal/usage/guides/data) folder and, optionally, adjust the name to your liking.
3. Open the Excel file and remove, edit or add to the values as you desire (e.g. your own orders). This is the default template that is also loaded in with `load --example`.
4. Open up the OpenBB Terminal, go to `portfolio` and type `load --file`. Your Excel file should then be one of the options.
:::

Note that the Excel sheet requires the following columns:

- **Date** - The date the trade occurred
- **Name** - The name of the security
- **Type** - The type of the security. Use Stock/Crypto/ETF as appropriate
- **Price** - The price the security was added or removed at, on a per-unit
  basis
- **Quantity** - How much of the security in question was added or removed
- **Side** - Whether you bought or sold. Use Buy/Deposit/1 to add to the
  portfolio or Sell/Withdrawal/0 to remove from the portfolio a search criteria,
  country, sector or industry.

The template Excel file also has additional columns but these are _optional_. The OpenBB Terminal can figure out by itself what industry, sector, country and region belongs to the loaded in Equity. So the field can be left blank if your holdings do not include this information.

Continuing with the example, this results in the following:

```
(🦋) /portfolio/ $ load --example

Loading an example, please type `about` to learn how to create your own Portfolio Excel sheet.

Preprocessing transactions: 100%|██████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████| 14/14 [00:02<00:00,  4.88it/s]
        Loading price data: 100%|████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████| 1/1 [00:00<00:00,  1.83it/s]
       Calculating returns: 100%|████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████| 1/1 [00:00<00:00,  2.46it/s]
         Loading benchmark: 100%|████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████| 4/4 [00:01<00:00,  2.35it/s]

Portfolio: OpenBB Example Portfolio
Risk Free Rate: 0.00%
Benchmark: SPDR S&P 500 ETF Trust (SPY)
```

With the <a href="/terminal/reference/portfolio/show" target="_blank" rel="noreferrer noopener">show</a> command we can show how the data has been loaded in:

```
2022 Jul 19, 10:03 (🦋) /portfolio/ $ show

┏━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━┳━━━━━━━┳━━━━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━┳━━━━━━━━┳━━━━━━━━━━┳━━━━━━┳━━━━━━━━━┳━━━━━━━━━━━━┳━━━━━━┳━━━━━━━━━━┓
┃ Date                ┃ Ticker ┃ Type  ┃ Sector                 ┃ Industry                            ┃ Country       ┃ Region        ┃ Price  ┃ Quantity ┃ Fees ┃ Premium ┃ Investment ┃ Side ┃ Currency ┃
┡━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━╇━━━━━━━╇━━━━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━━━━╇━━━━━━━━━━━━━━━╇━━━━━━━━╇━━━━━━━━━━╇━━━━━━╇━━━━━━━━━╇━━━━━━━━━━━━╇━━━━━━╇━━━━━━━━━━┩
│ 2010-05-03 00:00:00 │ GOOGL  │ STOCK │ Communication Services │ Internet Content & Information      │ United States │ North America │ 13.27  │ 2        │ 5    │ 6       │ 21.54      │ 1    │ USD      │
├─────────────────────┼────────┼───────┼────────────────────────┼─────────────────────────────────────┼───────────────┼───────────────┼────────┼──────────┼──────┼─────────┼────────────┼──────┼──────────┤
│ 2010-07-06 00:00:00 │ AMZN   │ STOCK │ Technology             │ Internet Retail                     │ United States │ North America │ 5.50   │ 5        │ 3    │ 3       │ 24.50      │ 1    │ USD      │
├─────────────────────┼────────┼───────┼────────────────────────┼─────────────────────────────────────┼───────────────┼───────────────┼────────┼──────────┼──────┼─────────┼────────────┼──────┼──────────┤
│ 2011-08-06 00:00:00 │ AAPL   │ STOCK │ Technology             │ Consumer Electronics                │ United States │ North America │ 12.61  │ 3        │ 1    │ 0       │ 36.83      │ 1    │ USD      │
├─────────────────────┼────────┼───────┼────────────────────────┼─────────────────────────────────────┼───────────────┼───────────────┼────────┼──────────┼──────┼─────────┼────────────┼──────┼──────────┤
│ 2011-12-12 00:00:00 │ APTV   │ STOCK │ Consumer Cyclical      │ Auto Parts                          │ United States │ North America │ 18.02  │ 5        │ 0    │ 2       │ 90.10      │ 1    │ USD      │
├─────────────────────┼────────┼───────┼────────────────────────┼─────────────────────────────────────┼───────────────┼───────────────┼────────┼──────────┼──────┼─────────┼────────────┼──────┼──────────┤
│ 2012-02-03 00:00:00 │ ASML   │ STOCK │ Technology             │ Semiconductor Equipment & Materials │ Netherlands   │ Europe        │ 59.17  │ 7        │ 0    │ 4       │ 414.19     │ 1    │ USD      │
├─────────────────────┼────────┼───────┼────────────────────────┼─────────────────────────────────────┼───────────────┼───────────────┼────────┼──────────┼──────┼─────────┼────────────┼──────┼──────────┤
│ 2012-05-04 00:00:00 │ NKE    │ STOCK │ Consumer Cyclical      │ Footwear & Accessories              │ Germany       │ Europe        │ 27.95  │ 3        │ 0    │ 0       │ 83.85      │ 1    │ USD      │
├─────────────────────┼────────┼───────┼────────────────────────┼─────────────────────────────────────┼───────────────┼───────────────┼────────┼──────────┼──────┼─────────┼────────────┼──────┼──────────┤
│ 2012-08-04 00:00:00 │ TSM    │ STOCK │ Technology             │ Semiconductors                      │ Taiwan        │ Asia          │ 14.24  │ 50       │ 0    │ 0       │ 712.00     │ 1    │ USD      │
├─────────────────────┼────────┼───────┼────────────────────────┼─────────────────────────────────────┼───────────────┼───────────────┼────────┼──────────┼──────┼─────────┼────────────┼──────┼──────────┤
│ 2012-10-12 00:00:00 │ DGX    │ STOCK │ Healthcare             │ Diagnostics & Research              │ United States │ North America │ 63.39  │ 6        │ 10   │ 0       │ 370.34     │ 1    │ USD      │
├─────────────────────┼────────┼───────┼────────────────────────┼─────────────────────────────────────┼───────────────┼───────────────┼────────┼──────────┼──────┼─────────┼────────────┼──────┼──────────┤
<continues>
```

After loading in the portfolio, it is time to select a benchmark. By default, this is set to <a href="https://www.ssga.com/us/en/individual/etfs/funds/spdr-sp-500-etf-trust-spy" target="_blank" rel="noreferrer noopener">SPDR S&P 500 ETF Trust (SPY)</a>. It is important to choose a benchmark that closely matches your portfolio so that you can understand if the trades you have made actually were beneficial. For example, let's load in the  with the <a href="/terminal/reference/portfolio/bench" target="_blank" rel="noreferrer noopener">bench</a> command as follows:

```
(🦋) /portfolio/ $ bench --benchmark VTI

         Loading benchmark: 100%|████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████| 4/4 [00:01<00:00,  2.91it/s]

(🦋) /portfolio/ $ ?

╭─────────────────────────────────────────────────────────────────────────────────────── Portfolio ───────────────────────────────────────────────────────────────────────────────────────╮
│                                                                                                                                                                                         │
│                                                                                                                                                                                         │
│ >   bro              brokers holdings,           supports: robinhood, ally, degiro, coinbase                                                                                            │
│ >   po               portfolio optimization,     optimize your portfolio weights efficiently                                                                                            │
│                                                                                                                                                                                         │
│     load             load data into the portfolio                                                                                                                                       │
│     show             show existing transactions                                                                                                                                         │
│     bench            define the benchmark                                                                                                                                               │
│                                                                                                                                                                                         │
│ Loaded transactions file: OpenBB Example Portfolio                                                                                                                                      │
│ Risk Free Rate:   0.00%                                                                                                                                                                 │
│ Benchmark: Vanguard Total Stock Market ETF (VTI)      
<continues>
```

Note that the `bench` command has a large selection of products you can choose from. Instead of taking the index directly, an ETF product is used to represent something that you could have actually invested in. By using the `DOWN` (⌄) arrow and pressing `ENTER` (⏎) you can select a different benchmark.

With `perf`, we can see how the portfolio performed compared to if you invested the same amount of money into the benchmark instead. This reflects the capabilities of you, as an investor, to outperform a passive strategy.

```
(🦋) /portfolio/ $ perf

     Portfolio vs. Benchmark - Totals in period: all
┏━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━┳━━━━━━━━━━━┳━━━━━━━━━━━━┓
┃                  ┃ Portfolio ┃ Benchmark ┃ Difference ┃
┡━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━╇━━━━━━━━━━━╇━━━━━━━━━━━━┩
│ Total Investment │ 47665.95  │ 47665.95  │ -          │
├──────────────────┼───────────┼───────────┼────────────┤
│ Total Value      │ 59961.16  │ 60038.37  │ -77.21     │
├──────────────────┼───────────┼───────────┼────────────┤
│ Total % Return   │ 25.79%    │ 25.96%    │ -0.16%     │
├──────────────────┼───────────┼───────────┼────────────┤
│ Total Abs Return │ 12295.21  │ 12372.42  │ -77.21     │
└──────────────────┴───────────┴───────────┴────────────┘
```

Compliment this by showing the volatility of the portfolio for different time periods with `metric` as follows:

```
(🦋) /portfolio/ $ metric volatility

Volatility for Portfolio and Benchmark
┏━━━━━┳━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━┓
┃     ┃ Portfolio [%] ┃ Benchmark [%] ┃
┡━━━━━╇━━━━━━━━━━━━━━━╇━━━━━━━━━━━━━━━┩
│ mtd │ 8.185         │ 4.210         │
├─────┼───────────────┼───────────────┤
│ qtd │ 8.185         │ 4.210         │
├─────┼───────────────┼───────────────┤
│ ytd │ 31.497        │ 18.220        │
├─────┼───────────────┼───────────────┤
│ 3m  │ 22.340        │ 14.436        │
├─────┼───────────────┼───────────────┤
│ 6m  │ 30.879        │ 17.912        │
├─────┼───────────────┼───────────────┤
│ 1y  │ 35.816        │ 20.128        │
├─────┼───────────────┼───────────────┤
│ 3y  │ 54.981        │ 41.174        │
├─────┼───────────────┼───────────────┤
│ 5y  │ 64.408        │ 45.647        │
├─────┼───────────────┼───────────────┤
│ 10y │ 78.014        │ 53.200        │
├─────┼───────────────┼───────────────┤
│ all │ 93.956        │ 60.885        │
└─────┴───────────────┴───────────────┘
```

## Examples

Starting off by loading in the OpenBB Example Portfolio again and changing the benchmark, the <a href="https://investor.vanguard.com/investment-products/etfs/profile/vti" target="_blank" rel="noreferrer noopener">Vanguard Total Stock Market ETF (VTI)</a>.

```
(🦋) /portfolio/ $ load --example

Loading an example, please type `about` to learn how to create your own Portfolio Excel sheet.

Preprocessing transactions: 100%|██████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████| 14/14 [00:02<00:00,  4.88it/s]
        Loading price data: 100%|████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████| 1/1 [00:00<00:00,  1.83it/s]
       Calculating returns: 100%|████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████| 1/1 [00:00<00:00,  2.46it/s]
         Loading benchmark: 100%|████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████| 4/4 [00:01<00:00,  2.35it/s]

Portfolio: OpenBB Example Portfolio
Risk Free Rate: 0.00%
Benchmark: SPDR S&P 500 ETF Trust (SPY)

(🦋) /portfolio/ $ bench VTI

         Loading benchmark: 100%|████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████| 4/4 [00:01<00:00,  3.32it/s]
```

Then, we can show our performance compared to that of the benchmark with `perf` as well as show the rolling beta with `rbeta`.

```
(🦋) /portfolio/ $ perf

     Portfolio vs. Benchmark - Totals in period: all
┏━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━┳━━━━━━━━━━━┳━━━━━━━━━━━━┓
┃                  ┃ Portfolio ┃ Benchmark ┃ Difference ┃
┡━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━╇━━━━━━━━━━━╇━━━━━━━━━━━━┩
│ Total Investment │ 47665.95  │ 47665.95  │ -          │
├──────────────────┼───────────┼───────────┼────────────┤
│ Total Value      │ 60815.22  │ 58901.42  │ 1913.79    │
├──────────────────┼───────────┼───────────┼────────────┤
│ Total % Return   │ 27.59%    │ 23.57%    │ 4.02%      │
├──────────────────┼───────────┼───────────┼────────────┤
│ Total Abs Return │ 13149.27  │ 11235.47  │ 1913.79    │
└──────────────────┴───────────┴───────────┴────────────┘

(🦋) /portfolio/ $ rbeta
```

![Rolling Beta of the Portfolio](https://user-images.githubusercontent.com/46355364/180178392-96efb6e1-60a1-4f76-92d8-434fb3637c21.png)

This helps in understanding that, even though you achieved a superior return, this also came at a greater risk compared to that of the benchmark. With the available functionalities you can further look into these results, e.g. by looking at the `summary` statistics:

```
🦋) /portfolio/ $ summary

Summary of Portfolio vs Benchmark for all period
┏━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━┳━━━━━━━━━━━┓
┃                   ┃ Portfolio ┃ Benchmark ┃
┡━━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━╇━━━━━━━━━━━┩
│ Volatility        │ 0.02      │ 0.01      │
├───────────────────┼───────────┼───────────┤
│ Skew              │ -1.65     │ -0.58     │
├───────────────────┼───────────┼───────────┤
│ Kurtosis          │ 32.89     │ 12.12     │
├───────────────────┼───────────┼───────────┤
│ Maximum Drawdowwn │ -0.42     │ -0.35     │
├───────────────────┼───────────┼───────────┤
│ Sharpe ratio      │ 0.04      │ 0.05      │
├───────────────────┼───────────┼───────────┤
│ Sortino ratio     │ 0.05      │ 0.06      │
├───────────────────┼───────────┼───────────┤
│ R2 Score          │ 0.50      │ 0.50      │
└───────────────────┴───────────┴───────────┘
```

As well as look into how the allocations differ per sector and country with `alloc`. This shows that there is a clear difference in how the benchmark and the portfolio are constructed implying the Total Market ETF might not be the best benchmark for your portfolio.

```
(🦋) /portfolio/ $ alloc sectors


      Portfolio vs. Benchmark - Top 4 Sectors Allocation
┏━━━━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━┳━━━━━━━━━━━┳━━━━━━━━━━━━┓
┃ Sectors                ┃ Portfolio ┃ Benchmark ┃ Difference ┃
┡━━━━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━╇━━━━━━━━━━━╇━━━━━━━━━━━━┩
│ Technology             │ 58.26%    │ 23.37%    │ 34.89%     │
├────────────────────────┼───────────┼───────────┼────────────┤
│ Consumer Cyclical      │ 30.26%    │ 10.30%    │ 19.96%     │
├────────────────────────┼───────────┼───────────┼────────────┤
│ Healthcare             │ 9.98%     │ 14.85%    │ -4.87%     │
├────────────────────────┼───────────┼───────────┼────────────┤
│ Communication Services │ 1.50%     │ 7.98%     │ -6.48%     │
└────────────────────────┴───────────┴───────────┴────────────┘

(🦋) /portfolio/ $ alloc countries


 Portfolio vs. Benchmark - Top 5 Countries Allocation
┏━━━━━━━━━━━━━━━┳━━━━━━━━━━━┳━━━━━━━━━━━┳━━━━━━━━━━━━┓
┃ Countries     ┃ Portfolio ┃ Benchmark ┃ Difference ┃
┡━━━━━━━━━━━━━━━╇━━━━━━━━━━━╇━━━━━━━━━━━╇━━━━━━━━━━━━┩
│ Netherlands   │ 38.06%    │ -         │ 38.06%     │
├───────────────┼───────────┼───────────┼────────────┤
│ United States │ 29.69%    │ 99.10%    │ -69.41%    │
├───────────────┼───────────┼───────────┼────────────┤
│ Taiwan        │ 14.66%    │ 0.01%     │ 14.65%     │
├───────────────┼───────────┼───────────┼────────────┤
│ China         │ 11.11%    │ -         │ 11.11%     │
├───────────────┼───────────┼───────────┼────────────┤
│ Ireland       │ 6.47%     │ -         │ 6.47%      │
└───────────────┴───────────┴───────────┴────────────┘
```
