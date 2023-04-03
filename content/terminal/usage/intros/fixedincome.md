---
title: Fixed Income
keywords: [fixed income, government bonds, bonds, corporate bonds, fixed, income, interest, rates, inflation, central bank, reference, rates, sofr, sonia, ester, estr]
description: The Fixed Income menu is the high-level menu for the Fixed Income asset class. It contains reference rates, central bank rates, government bonds, yield curves, corporate bond benchmarks and more.
---

The Fixed Income menu is the high-level menu for the Fixed Income asset class. It contains reference rates (ESTER, SOFR, SONIA and Ameribor), central bank rates (FRED, FOMC projections and ECB key interest rates), government bonds (treasury rates for any country, us-specific rates, yield curves), corporate bonds (ICE BofA Corporate Indices, Moody's AAA and BAA Corporate Indices, Commercial Paper, Spot Rates and HQM Corporate Yield Curve) and spread (ICE BofA spreads, constant maturity spreads, and federal funds rate)

## How to Use

The Fixed Income menu can be accessed directly from the `home` screen by typing `fixedincome`. This opens the menu as shown below. The menu heavily relies on FRED to obtain the data as seen below, please refer to the [API keys guide](https://docs.openbb.co/terminal/quickstart/api-keys) for information on how to obtain and set a key for FRED.

![Fixed Income Menu](https://user-images.githubusercontent.com/46355364/220970904-d32a63b5-aa14-47b4-bfe6-b5efc1cf2cd4.png)

## Examples
Starting off by calling some reference rates, these can be either `estr`, `sofr`, `sonia` or `ameribor`. For example the 1 year term structure of Ameribor is plotted with ` ameribor --parameter 1_year_term_structure` as shown below.

![Ameribor](https://user-images.githubusercontent.com/46355364/220971559-341f3144-b902-479d-998f-b68face9ba47.png)

The two most prominent central bank rates, those of the Federal Reserve and the European Central Bank can be plotted with `fed` and `ecb` respectively. For instance `fed` plots the monthly Federal Funds Rate.

![FED](https://user-images.githubusercontent.com/46355364/220971850-3ce5db4c-810a-49ba-a0bc-9043aa2a6090.png)

This can be accompanied with the projections, officially published by the FOMC. Here the long run expectations are plotted, which also backtracks several years, with `projection --long-run`:

![Projection](https://user-images.githubusercontent.com/46355364/220972251-688b12de-cf06-4907-9857-edda4aac64fb.png)

The European Central Bank rates can be shown with `ecb`. The ECB publishes three different rates that can be shown separately with ` ecb --type deposit` for example or plotted together with `ecb` as shown below.

![ECB](https://user-images.githubusercontent.com/46355364/220972670-0e5b11c6-7174-497a-ad18-36266e6a68c6.png)

In terms of government bonds, any combination of short term (3 month) and long term (10 year) government bonds for any country can be plotted with `treasury` for example `treasury --short canada,united_states --long canada,united_states` as shown below.

![Treasury Rates](https://user-images.githubusercontent.com/46355364/220973452-f7bdd468-e4fd-4c7a-aa45-3ce3c41f1f33.png)

With all of these functionalities, it is always possible to `--export` to Excel or show the raw data with `--raw` as shown below:

```
(🦋) /fixedincome/ $ treasury --short canada,united_states --long canada,united_states --raw

                                   Short and Long Term Interest Rates
┏━━━━━━━━━━━━┳━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━━━━━━━━━━━┓
┃            ┃ canada (3 month) ┃ united_states (3 month) ┃ canada (10 year) ┃ united_states (10 year) ┃
┡━━━━━━━━━━━━╇━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━━━━━━━━━━━━━━┩
│ 2022-04-01 │ 2.704            │ 2.750                   │ 1.347            │ 0.910                   │
├────────────┼──────────────────┼─────────────────────────┼──────────────────┼─────────────────────────┤
│ 2022-05-01 │ 2.919            │ 2.900                   │ 1.782            │ 1.330                   │
├────────────┼──────────────────┼─────────────────────────┼──────────────────┼─────────────────────────┤
│ 2022-06-01 │ 3.315            │ 3.140                   │ 2.247            │ 1.870                   │
├────────────┼──────────────────┼─────────────────────────┼──────────────────┼─────────────────────────┤
│ 2022-07-01 │ 3.043            │ 2.900                   │ 3.014            │ 2.500                   │
├────────────┼──────────────────┼─────────────────────────┼──────────────────┼─────────────────────────┤
│ 2022-08-01 │ 2.859            │ 2.900                   │ 3.382            │ 2.760                   │
├────────────┼──────────────────┼─────────────────────────┼──────────────────┼─────────────────────────┤
│ 2022-09-01 │ 3.148            │ 3.520                   │ 3.792            │ 3.210                   │
├────────────┼──────────────────┼─────────────────────────┼──────────────────┼─────────────────────────┤
│ 2022-10-01 │ 3.381            │ 3.980                   │ 4.231            │ 3.850                   │
├────────────┼──────────────────┼─────────────────────────┼──────────────────┼─────────────────────────┤
│ 2022-11-01 │ 3.166            │ 3.890                   │ 4.376            │ 4.460                   │
├────────────┼──────────────────┼─────────────────────────┼──────────────────┼─────────────────────────┤
│ 2022-12-01 │ 2.942            │ 3.620                   │ 4.553            │ 4.510                   │
├────────────┼──────────────────┼─────────────────────────┼──────────────────┼─────────────────────────┤
│ 2023-01-01 │ 2.938            │ 3.530                   │ 4.764            │ 4.610                   │
└────────────┴──────────────────┴─────────────────────────┴──────────────────┴─────────────────────────┘
```

For both the United States and the Eurozone, it is possible to see the current government bond yield curve. For the Eurozone, it is an aggregation of countries that match a specific credit rating, by default AAA, as shown with `ecbycrv`.

![Euro Area Yield Curve](https://user-images.githubusercontent.com/46355364/220974746-bd0fcf31-1108-458f-8f0f-893d3704ad7b.png)

When it comes to Corporate Bonds, the major indices are included. These are the ICE BofA indices and the Moody's Aaa and Baa indices. Based on a query, specific benchmarks can be found. For example a collection of indices matching a variety of bond maturities with `icebofa --duration`.

![ICE BOFA](https://user-images.githubusercontent.com/46355364/220975450-c3940875-8f47-48ca-9e19-c736bbc3f733.png)

The Moody's Aaa is often referred to as a great alternative to the federal ten-year Treasury bill as an indicator for interest rates and can be plotted with `moody`:

![Moody](https://user-images.githubusercontent.com/46355364/220976111-419e0b42-3ae8-41d4-8e41-95774be42a64.png)

Next to that, there are spot rates available for the High Quality Market (HQM) ranging from 1 year to a 100 years through `spot`. With this, it is also possible to plot the yield curve with `hqm` for any date in the past. For example `hqm --date 2020-01-01` as shown below:

![HQM](https://user-images.githubusercontent.com/46355364/220976622-58bcab69-4901-4b00-99d4-7462082a088d.png)

Furthermore, it is possible to see spreads between a variety of assets. For example the Emerging Markets spread can be shown with `icespread --category all --area emea`. This is based on the spot treasury curve.

![Emerging Market Spread](https://user-images.githubusercontent.com/46355364/220977016-98bde6f5-7432-40c4-a07b-598199c7381d.png)

For both `icebofa` and `icespread` it is possible to see all the options with `--options`. Find an example for `icespread` below.

```
(🦋) /fixedincome/ $ icespread --options

┏━━━━━━━━┳━━━━━━━━━━┳━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┓
┃ Type   ┃ Category ┃ Area          ┃ Grade          ┃ Title                                                                                                 ┃
┡━━━━━━━━╇━━━━━━━━━━╇━━━━━━━━━━━━━━━╇━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┩
│ spread │ duration │ us            │ non_sovereign  │ ICE BofA 1-3 Year US Corporate Index Option-Adjusted Spread                                           │
├────────┼──────────┼───────────────┼────────────────┼───────────────────────────────────────────────────────────────────────────────────────────────────────┤
│ spread │ duration │ us            │ non_sovereign  │ ICE BofA 3-5 Year US Corporate Index Option-Adjusted Spread                                           │
├────────┼──────────┼───────────────┼────────────────┼───────────────────────────────────────────────────────────────────────────────────────────────────────┤
│ spread │ duration │ us            │ non_sovereign  │ ICE BofA 5-7 Year US Corporate Index Option-Adjusted Spread                                           │
├────────┼──────────┼───────────────┼────────────────┼───────────────────────────────────────────────────────────────────────────────────────────────────────┤
│ spread │ duration │ us            │ non_sovereign  │ ICE BofA 7-10 Year US Corporate Index Option-Adjusted Spread                                          │
├────────┼──────────┼───────────────┼────────────────┼───────────────────────────────────────────────────────────────────────────────────────────────────────┤
│ spread │ duration │ us            │ non_sovereign  │ ICE BofA 10-15 Year US Corporate Index Option-Adjusted Spread                                         │
├────────┼──────────┼───────────────┼────────────────┼───────────────────────────────────────────────────────────────────────────────────────────────────────┤
│ spread │ duration │ us            │ non_sovereign  │ ICE BofA 15+ Year US Corporate Index Option-Adjusted Spread                                           │
├────────┼──────────┼───────────────┼────────────────┼───────────────────────────────────────────────────────────────────────────────────────────────────────┤
│ spread │ all      │ us            │ non_sovereign  │ ICE BofA US Corporate Index Option-Adjusted Spread                                                    │
├────────┼──────────┼───────────────┼────────────────┼───────────────────────────────────────────────────────────────────────────────────────────────────────┤
│ spread │ usd      │ us            │ high_yield     │ ICE BofA US High Yield Index Option-Adjusted Spread                                                   │
├────────┼──────────┼───────────────┼────────────────┼───────────────────────────────────────────────────────────────────────────────────────────────────────┤
│ spread │ eur      │ eu            │ high_yield     │ ICE BofA Euro High Yield Index Option-Adjusted Spread                                                 │
├────────┼──────────┼───────────────┼────────────────┼───────────────────────────────────────────────────────────────────────────────────────────────────────┤
│ spread │ all      │ ex_g10        │ non_sovereign  │ ICE BofA Emerging Markets Corporate Plus Index Option-Adjusted Spread                                 │
├────────┼──────────┼───────────────┼────────────────┼───────────────────────────────────────────────────────────────────────────────────────────────────────┤
│ spread │ all      │ ex_g10        │ private_sector │ ICE BofA Private Sector Financial Emerging Markets Corporate Plus Index Option-Adjusted Spread        │
├────────┼──────────┼───────────────┼────────────────┼───────────────────────────────────────────────────────────────────────────────────────────────────────┤
│ spread │ usd      │ ex_g10        │ non_sovereign  │ ICE BofA US Emerging Markets Corporate Plus Index Option-Adjusted Spread                              │
├────────┼──────────┼───────────────┼────────────────┼───────────────────────────────────────────────────────────────────────────────────────────────────────┤
│ spread │ eur      │ ex_g10        │ non_sovereign  │ ICE BofA Euro Emerging Markets Corporate Plus Index Option-Adjusted Spread                            │
├────────┼──────────┼───────────────┼────────────────┼───────────────────────────────────────────────────────────────────────────────────────────────────────┤
│ spread │ usd      │ ex_g10        │ non_sovereign  │ ICE BofA US Emerging Markets Liquid Corporate Plus Index Option-Adjusted Spread                       │
├────────┼──────────┼───────────────┼────────────────┼───────────────────────────────────────────────────────────────────────────────────────────────────────┤
│ spread │ usd      │ ex_g10        │ non_financial  │ ICE BofA Non-Financial US Emerging Markets Liquid Corporate Plus Index Option-Adjusted Spread         │
├────────┼──────────┼───────────────┼────────────────┼───────────────────────────────────────────────────────────────────────────────────────────────────────┤
│ spread │ usd      │ ex_g10        │ public_sector  │ ICE BofA Public Sector Issuers US Emerging Markets Liquid Corporate Plus Index Option-Adjusted Spread │
├────────┼──────────┼───────────────┼────────────────┼───────────────────────────────────────────────────────────────────────────────────────────────────────┤
│ spread │ all      │ emea          │ non_sovereign  │ ICE BofA EMEA Emerging Markets Corporate Plus Index Option-Adjusted Spread                            │
├────────┼──────────┼───────────────┼────────────────┼───────────────────────────────────────────────────────────────────────────────────────────────────────┤
│ spread │ usd      │ emea          │ non_sovereign  │ ICE BofA EMEA US Emerging Markets Liquid Corporate Plus Index Option-Adjusted Spread                  │
├────────┼──────────┼───────────────┼────────────────┼───────────────────────────────────────────────────────────────────────────────────────────────────────┤
│ spread │ all      │ asia          │ non_sovereign  │ ICE BofA Asia Emerging Markets Corporate Plus Index Option-Adjusted Spread                            │
├────────┼──────────┼───────────────┼────────────────┼───────────────────────────────────────────────────────────────────────────────────────────────────────┤
│ spread │ usd      │ asia          │ non_sovereign  │ ICE BofA Asia US Emerging Markets Liquid Corporate Plus Index Option-Adjusted Spread                  │
├────────┼──────────┼───────────────┼────────────────┼───────────────────────────────────────────────────────────────────────────────────────────────────────┤
│ spread │ all      │ latin_america │ non_sovereign  │ ICE BofA Latin America Emerging Markets Corporate Plus Index Option-Adjusted Spread                   │
├────────┼──────────┼───────────────┼────────────────┼───────────────────────────────────────────────────────────────────────────────────────────────────────┤
│ spread │ usd      │ latin_america │ non_sovereign  │ ICE BofA Latin America US Emerging Markets Liquid Corporate Plus Index Option-Adjusted Spread         │
├────────┼──────────┼───────────────┼────────────────┼───────────────────────────────────────────────────────────────────────────────────────────────────────┤
│ spread │ all      │ ex_g10        │ aaa            │ ICE BofA AAA-A Emerging Markets Corporate Plus Index Option-Adjusted Spread                           │
├────────┼──────────┼───────────────┼────────────────┼───────────────────────────────────────────────────────────────────────────────────────────────────────┤
│ spread │ usd      │ ex_g10        │ aaa            │ ICE BofA AAA-A US Emerging Markets Liquid Corporate Plus Index Option-Adjusted Spread                 │
├────────┼──────────┼───────────────┼────────────────┼───────────────────────────────────────────────────────────────────────────────────────────────────────┤
│ spread │ all      │ ex_g10        │ high_grade     │ ICE BofA High Grade Emerging Markets Corporate Plus Index Option-Adjusted Spread                      │
├────────┼──────────┼───────────────┼────────────────┼───────────────────────────────────────────────────────────────────────────────────────────────────────┤
│ spread │ all      │ ex_g10        │ bbb            │ ICE BofA BBB Emerging Markets Corporate Plus Index Option-Adjusted Spread                             │
├────────┼──────────┼───────────────┼────────────────┼───────────────────────────────────────────────────────────────────────────────────────────────────────┤
│ spread │ usd      │ ex_g10        │ bbb            │ ICE BofA BBB US Emerging Markets Liquid Corporate Plus Index Option-Adjusted Spread                   │
├────────┼──────────┼───────────────┼────────────────┼───────────────────────────────────────────────────────────────────────────────────────────────────────┤
│ spread │ all      │ ex_g10        │ crossover      │ ICE BofA Crossover Emerging Markets Corporate Plus Index Option-Adjusted Spread                       │
├────────┼──────────┼───────────────┼────────────────┼───────────────────────────────────────────────────────────────────────────────────────────────────────┤
│ spread │ all      │ ex_g10        │ bb             │ ICE BofA BB Emerging Markets Corporate Plus Index Option-Adjusted Spread                              │
├────────┼──────────┼───────────────┼────────────────┼───────────────────────────────────────────────────────────────────────────────────────────────────────┤
│ spread │ all      │ ex_g10        │ high_yield     │ ICE BofA High Yield Emerging Markets Corporate Plus Index Option-Adjusted Spread                      │
├────────┼──────────┼───────────────┼────────────────┼───────────────────────────────────────────────────────────────────────────────────────────────────────┤
│ spread │ all      │ ex_g10        │ b              │ ICE BofA B & Lower Emerging Markets Corporate Plus Index Option-Adjusted Spread                       │
├────────┼──────────┼───────────────┼────────────────┼───────────────────────────────────────────────────────────────────────────────────────────────────────┤
│ spread │ usd      │ us            │ aaa            │ ICE BofA AAA US Corporate Index Option-Adjusted Spread                                                │
├────────┼──────────┼───────────────┼────────────────┼───────────────────────────────────────────────────────────────────────────────────────────────────────┤
│ spread │ usd      │ us            │ aa             │ ICE BofA AA US Corporate Index Option-Adjusted Spread                                                 │
├────────┼──────────┼───────────────┼────────────────┼───────────────────────────────────────────────────────────────────────────────────────────────────────┤
│ spread │ usd      │ us            │ a              │ ICE BofA Single-A US Corporate Index Option-Adjusted Spread                                           │
├────────┼──────────┼───────────────┼────────────────┼───────────────────────────────────────────────────────────────────────────────────────────────────────┤
│ spread │ usd      │ us            │ bbb            │ ICE BofA BBB US Corporate Index Option-Adjusted Spread                                                │
├────────┼──────────┼───────────────┼────────────────┼───────────────────────────────────────────────────────────────────────────────────────────────────────┤
│ spread │ usd      │ us            │ bb             │ ICE BofA BB US High Yield Index Option-Adjusted Spread                                                │
├────────┼──────────┼───────────────┼────────────────┼───────────────────────────────────────────────────────────────────────────────────────────────────────┤
│ spread │ usd      │ us            │ b              │ ICE BofA Single-B US High Yield Index Option-Adjusted Spread                                          │
├────────┼──────────┼───────────────┼────────────────┼───────────────────────────────────────────────────────────────────────────────────────────────────────┤
│ spread │ usd      │ us            │ ccc            │ ICE BofA CCC & Lower US High Yield Index Option-Adjusted Spread                                       │
└────────┴──────────┴───────────────┴────────────────┴───────────────────────────────────────────────────────────────────────────────────────────────────────┘
```