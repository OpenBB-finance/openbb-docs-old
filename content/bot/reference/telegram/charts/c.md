---
########### THIS FILE IS AUTO GENERATED - ANY CHANGES WILL BE VOID ###########
title: c
description: OpenBB Telegram Command
---

# c

Chart for the crypto pair provided Default: 15m

### Usage

```python wordwrap
/c symbol [currency] [exchange] [interval] [srlines] [fibs]
```

---

## Parameters

| Name | Description | Optional | Choices |
| ---- | ----------- | -------- | ------- |
| symbol | Crypto Symbol | False | None |
| currency | Crypto Currency. Default: USDT | True | None |
| exchange | Crypto Exchange. Default: binanceus | True | None |
| interval | 1m: 1 Minute 3m: 3 Minutes 5m: 5 Minutes 15m: 15 Minutes 30m: 30 Minutes 1hr: 1 Hour 1d: 1 Day 1wk: 1 Week 1mo: 1 Month | True | 1m, 3m, 5m, 15m, 30m, 1hr, 1d, 1wk, 1mo |
| srlines | Show Support/Resistance Lines. Default: False | True | None |
| fibs | Show Fibonacci Retracement Levels. Default: False | True | None |


---

## Examples

```
/c doge
```

```
/c doge interval:3m
```
---
