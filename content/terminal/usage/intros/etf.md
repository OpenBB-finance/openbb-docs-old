---
title: ETF
keywords: [etfs, exchange traded funds, fund, basket, retail, stocks, openbb terminal]
description: The ETF menu enables you to lookup any ETF and obtain an overview about the chosen ETF. Furthermore, sub-menus reside in this menu that can be used to compare companies within the ETF, discover gainers and losers within discovery and apply advanced technical indicators. Lastly, it also has the option to export multiple ETFs to Excel.

---
The ETF menu enables you to lookup any ETF and obtain an <a href="/terminal/reference/etf/overview" target="_blank" rel="noreferrer noopener">overview</a>, <a href="/terminal/reference/etf/holdings" target="_blank" rel="noreferrer noopener">holdings</a>, <a href="/terminal/reference/etf/weights" target="_blank" rel="noreferrer noopener">weights</a> and <a href="/terminal/reference/etf/news" target="_blank" rel="noreferrer noopener">news</a> about the chosen ETF. Furthermore, sub-menus reside in this menu that can be used to <a href="/terminal/usage/intros/stocks/comparison" target="_blank" rel="noreferrer noopener">compare companies</a> within the ETF, discover gainers and losers within <a href="/terminal/reference#disc" target="_blank" rel="noreferrer noopener">discovery</a> and apply advanced <a href="/terminal/usage/intros/common/ta" target="_blank" rel="noreferrer noopener">technical indicators</a> and <a href="/terminal/usage/intros/forecast" target="_blank" rel="noreferrer noopener">Forecasting menu</a>. Lastly, it also has the option to export multiple ETFs to Excel with <a href="/terminal/reference/etf/pir" target="_blank" rel="noreferrer noopener">pir</a>.

### How to use

The ETF menu is called upon by typing `etf` which opens the following menu:

<img width="800" alt="image" src="https://user-images.githubusercontent.com/46355364/218991629-fcf0c38b-e690-4720-9510-494c4cb25dba.png"></img>

You now have the ability to look up any ETF. With the example below, the `load` command is used to load an ETF.

```
(🦋) /etf/ $ load voo

Loading Daily data for VOO with starting period 2022-02-08. 
```

Now we can use `holdings` to see the makeup of VOO

```
2022 Jun 21, 09:14 (🦋) /etf/ holdings

                                                          ETF Holdings
┌───────┬─────────────────────────────────┬──────────┬───────────┐
│       │ Name                            │ % Of Etf │ Shares    │
├───────┼─────────────────────────────────┼──────────┼───────────┤
│ AAPL  │ Apple Inc.                      │ 7.08%    │ 345662285 │
├───────┼─────────────────────────────────┼──────────┼───────────┤
│ MSFT  │ Microsoft Corporation           │ 5.29%    │ 170648491 │
├───────┼─────────────────────────────────┼──────────┼───────────┤
│ AMZN  │ Amazon.com, Inc.                │ 2.77%    │ 202804167 │
├───────┼─────────────────────────────────┼──────────┼───────────┤
│ TSLA  │ Tesla, Inc.                     │ 1.85%    │ 60944555  │
├───────┼─────────────────────────────────┼──────────┼───────────┤
│ GOOGL │ Alphabet, Inc.                  │ 1.73%    │ 137178918 │
├───────┼─────────────────────────────────┼──────────┼───────────┤
│ BRK.B │ Berkshire Hathaway Inc.         │ 1.63%    │ 41297378  │
├───────┼─────────────────────────────────┼──────────┼───────────┤
│ UNH   │ UnitedHealth Group Incorporated │ 1.59%    │ 21403214  │
├───────┼─────────────────────────────────┼──────────┼───────────┤
│ GOOG  │ Alphabet, Inc.                  │ 1.55%    │ 122705978 │
├───────┼─────────────────────────────────┼──────────┼───────────┤
│ XOM   │ Exxon Mobil Corporation         │ 1.41%    │ 95363206  │
├───────┼─────────────────────────────────┼──────────┼───────────┤
│ JNJ   │ Johnson & Johnson               │ 1.40%    │ 60159633  │
└───────┴─────────────────────────────────┴──────────┴───────────┘
```

To then view the stock chart, you can call <a href="/terminal/reference/etf/candle" target="_blank" rel="noreferrer noopener">candle</a> which shows a candle chart for the defined period (by default set to a year by `load`):

![Candle Chart of VOO](https://user-images.githubusercontent.com/46355364/174823545-6695f9b0-864c-4b94-a612-baa8087d1858.png)

The ETF's weights can now be depicted with the following:

```
(🦋) /etf/ $ weights
```

Which shows the following graph:

![Figure_1](https://user-images.githubusercontent.com/46355364/218991849-d75c51f7-2343-4614-ad26-0f435670f4f0.png)

## Examples

If we want to learn more about a total market ETF, we can do the following, starting from the `etf` menu and using the `ld` command where we specify with `-l` we wish to see `15` ETFs max.

```
(🦋) /etf/ $ search --description total market -l 15


                                                    ETFs by Total Assets
┏━━━━━━┳━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━━━━━━━━━━━━━┓
┃      ┃ Name                                               ┃ Family                            ┃ Category                  ┃
┡━━━━━━╇━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━━━━━━━━━━━━━━━━┩
│ VTI  │ Vanguard Total Stock Market Index Fund ETF Shares  │ Vanguard                          │ Large Blend               │
├──────┼────────────────────────────────────────────────────┼───────────────────────────────────┼───────────────────────────┤
│ ITOT │ iShares Core S&P Total U.S. Stock Market ETF       │ iShares                           │ Large Blend               │
├──────┼────────────────────────────────────────────────────┼───────────────────────────────────┼───────────────────────────┤
│ XBI  │ SPDR S&P Biotech ETF                               │ SPDR State Street Global Advisors │ Health                    │
├──────┼────────────────────────────────────────────────────┼───────────────────────────────────┼───────────────────────────┤
│ HYLB │ Xtrackers USD High Yield Corporate Bond ETF        │ Xtrackers                         │ High Yield Bond           │
├──────┼────────────────────────────────────────────────────┼───────────────────────────────────┼───────────────────────────┤
│ KRE  │ SPDR S&P Regional Banking ETF                      │ SPDR State Street Global Advisors │ Financial                 │
├──────┼────────────────────────────────────────────────────┼───────────────────────────────────┼───────────────────────────┤
│ XOP  │ SPDR S&P Oil & Gas Exploration & Production ETF    │ SPDR State Street Global Advisors │ Equity Energy             │
├──────┼────────────────────────────────────────────────────┼───────────────────────────────────┼───────────────────────────┤
│ XHB  │ SPDR S&P Homebuilders ETF                          │ SPDR State Street Global Advisors │ Consumer Cyclical         │
├──────┼────────────────────────────────────────────────────┼───────────────────────────────────┼───────────────────────────┤
│ XME  │ SPDR S&P Metals and Mining ETF                     │ SPDR State Street Global Advisors │ Natural Resources         │
├──────┼────────────────────────────────────────────────────┼───────────────────────────────────┼───────────────────────────┤
│ SCHK │ Schwab 1000 ETF                                    │ Schwab ETFs                       │ Large Blend               │
├──────┼────────────────────────────────────────────────────┼───────────────────────────────────┼───────────────────────────┤
│ XAR  │ SPDR S&P Aerospace & Defense ETF                   │ SPDR State Street Global Advisors │ Industrials               │
├──────┼────────────────────────────────────────────────────┼───────────────────────────────────┼───────────────────────────┤
│ FPXI │ First Trust International Equity Opportunities ETF │ First Trust                       │ Foreign Large Growth      │
├──────┼────────────────────────────────────────────────────┼───────────────────────────────────┼───────────────────────────┤
│ XSD  │ SPDR S&P Semiconductor ETF                         │ SPDR State Street Global Advisors │ Technology                │
├──────┼────────────────────────────────────────────────────┼───────────────────────────────────┼───────────────────────────┤
│ XHE  │ SPDR S&P Health Care Equipment ETF                 │ SPDR State Street Global Advisors │ Health                    │
├──────┼────────────────────────────────────────────────────┼───────────────────────────────────┼───────────────────────────┤
│ XRT  │ SPDR S&P Retail ETF                                │ SPDR State Street Global Advisors │ Consumer Cyclical         │
├──────┼────────────────────────────────────────────────────┼───────────────────────────────────┼───────────────────────────┤
│ UWM  │ ProShares Ultra Russell2000                        │ ProShares                         │ Trading--Leveraged Equity │
└──────┴────────────────────────────────────────────────────┴───────────────────────────────────┴───────────────────────────┘
```

It seems Vanguard Total Stock Market Index Fund ETF Shares (VTI) is by far the largest ETF in this list so let's <a href="/terminal/reference/etf/load" target="_blank" rel="noreferrer noopener">load</a> it in. Also, a larger period is chosen by using `-s` as shown in the documentation:

```
(🦋) /etf/ $ load VTI -s 2010-01-01

Loading Daily data for VTI with starting period 2010-01-01. 
```

We can now plot the corresponding ETF chart with <a href="/terminal/reference/etf/candle" target="_blank" rel="noreferrer noopener">candle</a> which shows the company's historical data from `2010-01-01` until the current date. We are also adding in trendlines with `-t`.

```
(🦋) /etf/ $ candle -t
```

![Candle Chart with Trendlines](https://user-images.githubusercontent.com/46355364/174823785-ec11cb1a-dbf0-45a7-b086-31542ece39a3.png)

Now we can go ahead and explore more about the ETF by running <a href="/terminal/reference/etf/holdings" target="_blank" rel="noreferrer noopener">holdings</a>.

```
(🦋) /etf/ $ holdings

                           ETF Holdings                           
┏━━━━━━━┳━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━┳━━━━━━━━━━━┓
┃       ┃ Name                            ┃ % Of Etf ┃ Shares    ┃
┡━━━━━━━╇━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━╇━━━━━━━━━━━┩
│ AAPL  │ Apple Inc.                      │ 5.37%    │ 463159883 │
├───────┼─────────────────────────────────┼──────────┼───────────┤
│ MSFT  │ Microsoft Corporation           │ 4.55%    │ 228457719 │
├───────┼─────────────────────────────────┼──────────┼───────────┤
│ AMZN  │ Amazon.com, Inc.                │ 2.20%    │ 265749029 │
├───────┼─────────────────────────────────┼──────────┼───────────┤
│ GOOGL │ Alphabet Inc.                   │ 1.45%    │ 182976022 │
├───────┼─────────────────────────────────┼──────────┼───────────┤
│ BRK.B │ Berkshire Hathaway Inc.         │ 1.29%    │ 51480271  │
├───────┼─────────────────────────────────┼──────────┼───────────┤
│ GOOG  │ Alphabet Inc.                   │ 1.27%    │ 158609478 │
├───────┼─────────────────────────────────┼──────────┼───────────┤
│ XOM   │ Exxon Mobil Corporation         │ 1.18%    │ 126216002 │
├───────┼─────────────────────────────────┼──────────┼───────────┤
│ UNH   │ UnitedHealth Group Incorporated │ 1.15%    │ 28636503  │
├───────┼─────────────────────────────────┼──────────┼───────────┤
│ TSLA  │ Tesla, Inc.                     │ 1.14%    │ 82259496  │
├───────┼─────────────────────────────────┼──────────┼───────────┤
│ NVDA  │ NVIDIA Corporation              │ 1.12%    │ 71628196  │
└───────┴─────────────────────────────────┴──────────┴───────────┘
```

And <a href="/terminal/reference/etf/weights" target="_blank" rel="noreferrer noopener">weights</a> using the `--raw` argument for weights to display a table instead of a graph.
```
(🦋) /etf/ $ weights --raw

   Sector Weightings Allocation    
┏━━━━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━┓
┃ Sector                 ┃ Weight ┃
┡━━━━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━┩
│ Real Estate            │ 3.51%  │
├────────────────────────┼────────┤
│ Consumer Cyclical      │ 12.08% │
├────────────────────────┼────────┤
│ Basic Materials        │ 2.54%  │
├────────────────────────┼────────┤
│ Consumer Defensive     │ 6.05%  │
├────────────────────────┼────────┤
│ Technology             │ 22.9%  │
├────────────────────────┼────────┤
│ Communication Services │ 10.29% │
├────────────────────────┼────────┤
│ Financial Services     │ 13.98% │
├────────────────────────┼────────┤
│ Utilities              │ 2.51%  │
├────────────────────────┼────────┤
│ Industrials            │ 9.78%  │
├────────────────────────┼────────┤
│ Energy                 │ 2.64%  │
├────────────────────────┼────────┤
│ Healthcare             │ 13.73% │
└────────────────────────┴────────┘
```
