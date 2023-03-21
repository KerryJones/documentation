---
title: STOCKQUOTE (Coming Soon)
sidebar_position: 2
---

:::caution Coming Soon
This formula is planned for the future and has not yet been implemented.
:::

Fetches real-time stock quote(s) from Market Data.

:::tip

Group all your stock quotes together and request them all at once with a single ```STOCKQUOTE``` formula to _significantly_ speed up your sheet's loading time and avoid Google's [urlfetch limits](/sheets-add-on/troubleshooting/urlfetch).

:::

## Sample Usage

    STOCKQUOTE("AAPL")
    STOCKQUOTE("AAPL", "bid")
    STOCKQUOTE("AAPL,MSFT,GOOG", "all")
    STOCKQUOTE({"AAPL";"MSFT";"GOOG"}, "all")
    STOCKQUOTE(A1:C1, "all")
    
## Syntax

    STOCKQUOTE(symbol, attributes)

- **symbol(s)** _(REQUIRED)_ The stock’s ticker symbol. Seperate multiple symbols with commas or use a single column array or a single column of cell references.
- **attributes** _(Optional)_ Use one of the following attributes when requesting a quote:
  - "symbol", "ticker" - The symbol for the stock.
  - "price", "mid", "mark" – The midpoint price of the stock.
  - "bid" – The bid price of the stock.
  - "ask" – The ask price of the stock.
  - "bid size" – The quantity of shares offered at the bid price.
  - "ask size" – The quantity of shares offered at the ask price.
  - "last" – The last price of the stock.
  - "volume" – The quantity of shares traded.
  - "date", "updated" - The date and time of the stock quote.
  - "all" – Returns all values.

## Notes

:::info

Results will be returned as a value within a single cell unless more than one attribute is requested.

---

All parameters must be enclosed in quotation marks or be references to cells containing text.

---

Dates and times are returned in the same timezone of the exchange.

:::