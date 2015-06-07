---
layout: post
title: Visualize Trades and Quotes
unlisted: false
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

The following illustration shows GOOG TAQ data on the NASDAQ OMX BX exchange over two hours' time.

The bid and ask are represented by two horizontal bars whose lengths are defined by quote size.

The left graph represents the data feed in its original CLOB form. The trades are represented by yellow stars whose sizes are defined by trade volume. (Translucency and horizontal noise are added so that accumulation is observable.)

The right graph represents a simulated FBA feed with an interval time of **360 seconds**. Analogous to the CLOB representation, the exchange BBO is denoted by the two bars. When an auction results in trading, the trades' aggregate is represented by a star at the clearing price, whose size is defined by aggregate volume.

<a href = "https://cdn.rawgit.com/TeddyCho/TeddyCho.github.io/master/_posts/img/goog2hours.gif"><img src="https://raw.githubusercontent.com/TeddyCho/TeddyCho.github.io/master/_posts/img/goog2hours.gif" /></a>

The following shows a simulated FBA feed with an interval time of **120 seconds**:

<a href = "https://cdn.rawgit.com/TeddyCho/TeddyCho.github.io/master/_posts/img/googhour120.gif"><img src="https://raw.githubusercontent.com/TeddyCho/TeddyCho.github.io/master/_posts/img/googhour120.gif" /></a>

The following shows a simulated FBA feed with an interval time of **1 second**:

<a href = "https://cdn.rawgit.com/TeddyCho/TeddyCho.github.io/master/_posts/img/googone.gif"><img src="https://raw.githubusercontent.com/TeddyCho/TeddyCho.github.io/master/_posts/img/googone.gif" /></a>

# To Do
* Given TAQ data, simulate the FBA better. Currently, it's just randomly choosing when the auction results in a trade or not, and otherwise mirroring CLOB. Differentiate between snipe trades and investor trades.
* Consider accounting for multiple exchanges.
