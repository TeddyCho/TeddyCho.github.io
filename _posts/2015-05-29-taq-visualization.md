---
layout: post
title: Visualize Trades and Quotes
unlisted: true
---

# Tasks
> * Visualize trades and quotes (TAQ) data.
>
> * Include a comparison of continuous limit order book (CLOB) and frequent batch auctions (FBA).

# Data
The TAQ data covered the following time frame and symbols:
<table>
  <thead>
    <tr>      <th>Timeframe</th> <th>Symbol</th> <th>Exchange</th>   </tr>
  </thead>
  <tbody>
    <tr>      <td>09-July-2014 to 09-July-2014</td>
      <td>GOOG</td> 
      <td>NASDAQ OMX BX</td> 
    </tr>
  </tbody>
</table>

# Visualization

The following illustration shows GOOG trades over an hour's time.

The bid and ask are represented by two horizontal bars whose length depends on their quote size.

The trades are represented by the yellow stars. Horizontal jittering and translucency is added so accumulation is observable.



# To Do
* Given TAQ data, simulate the FBA supply/demand curves and the resulting trades.
