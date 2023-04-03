---
title: Trading Hours
keywords: [markets, trading, hours, stocks, time, global, world, location, open, close, exchange]
description: An Introduction to the Trading Hours menu, within the Stocks menu. This set of features displays the status of international markets.
---
This set of features is for checking the operating status of markets globally. To access the Trading Hours features, enter `th` from the <a href="/terminal/usage/intros/stocks/" target="_blank" rel="noreferrer noopener">Stocks menu</a>. Alternatively, a user can access the submenu with absolute path navigation from anywhere in the Terminal: `/stocks/th`

<img width="800" alt="image" src="https://user-images.githubusercontent.com/46355364/218986176-7e995a97-8689-4440-beb8-43bde85f1a92.png"></img>

## How to use

A symbol is not required to be loaded. Once in the Trading Hours menu, the operation is simple. Choose from: <a href="/terminal/reference/stocks/th/open" target="_blank" rel="noreferrer noopener">open</a>, <a href="/terminal/reference/stocks/th/closed" target="_blank" rel="noreferrer noopener">closed</a>, <a href="/terminal/reference/stocks/th/all" target="_blank" rel="noreferrer noopener">all</a> or <a href="/terminal/reference/stocks/th/exchange" target="_blank" rel="noreferrer noopener">exchange</a>.

Below, examples are given what these commands display, note that the tables are purposely cut off to keep the introduction compact.

````
(🦋) /stocks/th/ $ open
                      Open markets
┏━━━━━┳━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━┓
┃     ┃ name                              ┃ short_name ┃
┡━━━━━╇━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━┩
│ FRA │ Frankfurt Stock Exchange          │ F          │
├─────┼───────────────────────────────────┼────────────┤
│ STU │ Börse Stuttgart                   │ SG         │
├─────┼───────────────────────────────────┼────────────┤
│ MUN │ Börse München                     │ MU         │
├─────┼───────────────────────────────────┼────────────┤
│ DUS │ Börse Düsseldorf                  │ DU         │
├─────┼───────────────────────────────────┼────────────┤
│ MEX │ Bolsa Mexicana de Valores         │ MX         │
├─────┼───────────────────────────────────┼────────────┤
│ FKA │ Frankfurt Stock Exchange          │ F          │
├─────┼───────────────────────────────────┼────────────┤
│ NYQ │ New York Stock Exchange           │ NYSE       │
├─────┼───────────────────────────────────┼────────────┤
│ VAN │ TSX Venture Exchange              │ V          │
├─────┼───────────────────────────────────┼────────────┤
<continues>

(🦋) /stocks/th/ $ closed
                    Closed markets
┏━━━━━┳━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━┓
┃     ┃ name                             ┃ short_name ┃
┡━━━━━╇━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━┩
│ SHZ │ Shenzen Stock Exchange           │ SHZE       │
├─────┼──────────────────────────────────┼────────────┤
│ KSC │ Korea Exchange                   │ KRX        │
├─────┼──────────────────────────────────┼────────────┤
│ KOE │ Korea Exchange                   │ KRX        │
├─────┼──────────────────────────────────┼────────────┤
│ HKG │ Hong Kong Stock Exchange         │ HKEX       │
├─────┼──────────────────────────────────┼────────────┤
│ KLS │ Bursa Malaysia                   │ KLSE       │
├─────┼──────────────────────────────────┼────────────┤
│ ENX │ Euronext                         │ NX         │
├─────┼──────────────────────────────────┼────────────┤
│ TWO │ Taipei Exchange                  │ TWO        │
├─────┼──────────────────────────────────┼────────────┤
│ HAM │ Hamburger Börse                  │ HM         │
├─────┼──────────────────────────────────┼────────────┤
│ TW  │ Taiwan Stock Exchange            │ TWSE       │
├─────┼──────────────────────────────────┼────────────┤
<continues>

(🦋) /stocks/th/ $ all
                         World markets
┏━━━━━┳━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━┳━━━━━━━┓
┃     ┃ name                              ┃ short_name ┃ open  ┃
┡━━━━━╇━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━╇━━━━━━━┩
│ SHZ │ Shenzen Stock Exchange            │ SHZE       │ False │
├─────┼───────────────────────────────────┼────────────┼───────┤
│ KSC │ Korea Exchange                    │ KRX        │ False │
├─────┼───────────────────────────────────┼────────────┼───────┤
│ KOE │ Korea Exchange                    │ KRX        │ False │
├─────┼───────────────────────────────────┼────────────┼───────┤
│ HKG │ Hong Kong Stock Exchange          │ HKEX       │ False │
├─────┼───────────────────────────────────┼────────────┼───────┤
│ KLS │ Bursa Malaysia                    │ KLSE       │ False │
├─────┼───────────────────────────────────┼────────────┼───────┤
│ FRA │ Frankfurt Stock Exchange          │ F          │ True  │
├─────┼───────────────────────────────────┼────────────┼───────┤
│ STU │ Börse Stuttgart                   │ SG         │ True  │
├─────┼───────────────────────────────────┼────────────┼───────┤
│ ENX │ Euronext                          │ NX         │ False │
├─────┼───────────────────────────────────┼────────────┼───────┤
│ TWO │ Taipei Exchange                   │ TWO        │ False │
├─────┼───────────────────────────────────┼────────────┼───────┤
│ HAM │ Hamburger Börse                   │ HM         │ False │
├─────┼───────────────────────────────────┼────────────┼───────┤
<continues>
````
Lastly, <a href="/terminal/reference/stocks/th/exchange" target="_blank" rel="noreferrer noopener">exchange</a> shows the status of a single venue.

```
(🦋) /stocks/th/ $ exchange --name ARCA

                            PCX    NYSE Arca
                       Name: name, dtype: object
┏━━━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┓
┃                       ┃ PCX                                          ┃
┡━━━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┩
│ name                  │ NYSE Arca                                    │
├───────────────────────┼──────────────────────────────────────────────┤
│ short_name            │ ARCA                                         │
├───────────────────────┼──────────────────────────────────────────────┤
│ website               │ https://www.nyse.com/markets/hours-calendars │
├───────────────────────┼──────────────────────────────────────────────┤
│ market_open           │ 09:30:00                                     │
├───────────────────────┼──────────────────────────────────────────────┤
│ market_close          │ 16:00:00                                     │
├───────────────────────┼──────────────────────────────────────────────┤
│ lunchbreak_start      │ None                                         │
├───────────────────────┼──────────────────────────────────────────────┤
│ lunchbreak_end        │ None                                         │
├───────────────────────┼──────────────────────────────────────────────┤
│ opening_auction_start │ 04:00:00                                     │
├───────────────────────┼──────────────────────────────────────────────┤
│ opening_auction_end   │ 09:30:00                                     │
├───────────────────────┼──────────────────────────────────────────────┤
│ closing_auction_start │ 16:00:00                                     │
├───────────────────────┼──────────────────────────────────────────────┤
│ closing_auction_end   │ 20:00:00                                     │
├───────────────────────┼──────────────────────────────────────────────┤
│ timezone              │ US/Eastern                                   │
├───────────────────────┼──────────────────────────────────────────────┤
│ flag                  │ 🇺🇸                                           │
├───────────────────────┼──────────────────────────────────────────────┤
│ open                  │ False                                        │
└───────────────────────┴──────────────────────────────────────────────┘
```

## Examples

Below an example is given for a symbol and whether that market is open. By calling <a href="/terminal/reference/stocks/th/exchange" target="_blank" rel="noreferrer noopener">exchange</a> you can obtain more information about the exchange (e.g. enter `BO`)
````
(🦋) /stocks/th/ $ symbol RY.TO

Selected symbol
Symbol:        RY.TO
Name:          ROYAL BANK OF CANADA
Market open:   False

(🦋) /stocks/th/ $ symbol FB2.L

Selected symbol
Symbol:        FB2.L
Name:          LEVERAGE SHARES PUBLIC LIMITED
Market open:   False

(🦋) /stocks/th/ $ exchange BO
┏━━━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┓
┃                       ┃ BSE                                                                       ┃
┡━━━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┩
│ name                  │ BSE                                                                       │
├───────────────────────┼───────────────────────────────────────────────────────────────────────────┤
│ short_name            │ BO                                                                        │
├───────────────────────┼───────────────────────────────────────────────────────────────────────────┤
│ website               │ https://www.bseindia.com/static/markets/equity/EQReports/tra_trading.aspx │
├───────────────────────┼───────────────────────────────────────────────────────────────────────────┤
│ market_open           │ 09:15:00                                                                  │
├───────────────────────┼───────────────────────────────────────────────────────────────────────────┤
│ market_close          │ 15:30:00                                                                  │
├───────────────────────┼───────────────────────────────────────────────────────────────────────────┤
│ lunchbreak_start      │ None                                                                      │
├───────────────────────┼───────────────────────────────────────────────────────────────────────────┤
│ lunchbreak_end        │ None                                                                      │
├───────────────────────┼───────────────────────────────────────────────────────────────────────────┤
│ opening_auction_start │ None                                                                      │
├───────────────────────┼───────────────────────────────────────────────────────────────────────────┤
│ opening_auction_end   │ None                                                                      │
├───────────────────────┼───────────────────────────────────────────────────────────────────────────┤
│ closing_auction_start │ None                                                                      │
├───────────────────────┼───────────────────────────────────────────────────────────────────────────┤
│ closing_auction_end   │ None                                                                      │
├───────────────────────┼───────────────────────────────────────────────────────────────────────────┤
│ timezone              │ Asia/Kolkata                                                              │
├───────────────────────┼───────────────────────────────────────────────────────────────────────────┤
│ flag                  │ 🇮🇳
├───────────────────────┼───────────────────────────────────────────────────────────────────────────┤
│ open                  │ False                                                                     │
└───────────────────────┴───────────────────────────────────────────────────────────────────────────┘
````
