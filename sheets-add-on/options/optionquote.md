---
title: OPTIONQUOTE (Coming Soon)
sidebar_position: 2
---

:::caution Coming Soon

This formula is planned for the future and has not yet been implemented.

:::

Fetches real-time option quote(s) from Market Data.

:::tip

Group all your option quotes together and request them all at once with a single ```OPTIONQUOTE``` formula to _significantly_ speed up your sheet's loading time and avoid Google's [urlfetch limits](/sheets-add-on/troubleshooting/urlfetch).

:::


## Sample Usage

    OPTIONQUOTE("AAPL250117C00150000")
    OPTIONQUOTE("AAPL250117C00150000", "bid")
    OPTIONQUOTE("AAPL250117C00150000,AAPL250117C00160000,AAPL250117C00170000", "bid,ask")
    OPTIONQUOTE(A1:G1, "all")

## Syntax

    OPTIONQUOTE("option symbols", "attributes")

- **option symbol(s)** _(REQUIRED)_ The OCC option symbol format for the option.
- **attribute(s)** _(OPTIONAL "price" by default)_ Use at least one of the following attributes; seperate multiple attributes with commas:
  - "symbol" - The OCC option symbol.
  - "date", "updated" - The date and time of the quote.
  - "price", "mid", "mark" – The midpoint price of the option.
  - "bid" – The bid price of the option.
  - "ask" – The ask price of the option.
  - "last" – The last price of the option. Depending on the liquidity of the symbol, the last traded price could have occurred one second ago or one day ago.
  - "bid size" – The quantity of contracts offered at the bid price.
  - "ask size" – The quantity of contracts offered at the ask price.
  - "volume" – The number of contracts negotiated during the day.
  - "open interest" – The number of open contracts.
  - "underlying price" – The price of the underlying security at the time of this option quote.
  - "in the money" – Will return TRUE if the option contract was in the money at the time of the quote or FALSE if the contract was not in the money at the time of the quote.
  - "intrinsic value" - The intrinsic value of the option, if any.
  - "extrinsic value" - The extrinsic or time value of the option.
  - "iv", "implied volatility" - The implied volatility of the option.
  - "delta" - The delta of the option.
  - "gamma" - The gamma of the option.
  - "theta" - The theta of the option.
  - "vega" - The vega of the option.
  - "rho" - The rho of the option.
  - "all" – Returns all values.
  - "noheaders" – Returns values without column headers.

## Notes

:::info

All parameters must be enclosed in quotation marks or be references to cells containing text. A possible exception is when endDate is specified as a number of days.

---

Results will be returned as a value within a single cell unless more than one attribute is requested.

---

Dates and times are returned in the same timezone of the exchange.

:::