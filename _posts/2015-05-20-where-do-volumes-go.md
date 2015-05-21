---
layout: post
title: Where Do Volumes Go?
unlisted: true
---

## Task
> 1. Using the TAQ data, compute the market shares for the different stock exchanges for a representative sample of stocks (it should include GOOG, BAC, and then a representative sample of other stocks, the size of the sample can depend on what's feasible computationally).
> 
> 2. Focus on calendar year 2014, and compute volumes and market shares for each exchange for each trading day, dividing the day into the opening auction, regular trading, closing auction, and after-hours trading.

## Data
Attributes of the raw TAQ data:
<table>
  <thead>
    <tr>      <th>Timeframe</th>      <th>Symbols</th>    </tr>
  </thead>
  <tbody>
    <tr>      <td>01-Jan-2014 to 31-Dec-2014</td>      <td>BAC, GOOG, BHP, BRKA, FE, RSH, SLV, T, XOM</td>    </tr>
  </tbody>
</table>
Computing per-day exchange shares on the above data, consisting of 64209422 rows, took 495 seconds on a 2.4 GHz/4GB laptop.

The raw output from the code is [here](https://github.com/TeddyCho/TeddyCho.github.io/blob/master/_posts/img/breakdown1.csv).

A trade's time of day was inferred from Sale Condition as follows:
<table>
  <thead>
    <tr>      <th>Time of Day</th>      <th>Sale Condition</th>    </tr>
  </thead>
  <tbody>
    <tr>      <td>Open</td>      <td>O, Q</td>    </tr>
    <tr>      <td>Close</td>      <td>M, 6</td>    </tr>
    <tr>      <td>After-Hours</td>      <td>T, U</td>    </tr>
    <tr>      <td>Regular</td>      <td>Everything else</td>    </tr>
  </tbody>
</table>


## Overall Look at Exchange Market Shares
[Over all trades, the volumes were distributed across exhanges as such.](http://rcharts.github.io/viewer/?a2c6f9b03902566cfb76)
<table>
  <thead>
    <tr><th>Exchange</th><th>Proportion</th></tr>
  </thead>
  <tbody>
    <tr><td>BATS</td><td>.05971</td></tr>
    <tr><td>BATS Y</td><td>.03509</td></tr>
    <tr><td>CBOE</td><td>.0008565</td></tr>
    <tr><td>Chicago</td><td>.006891</td></tr>
    <tr><td>Direct Edge A</td><td>.03483</td></tr>
    <tr><td>Direct Edge X</td><td>.07810</td></tr>
    <tr><td>FINRA</td><td>.3828</td></tr>
    <tr><td>NASDAQ</td><td>.005666</td></tr>
    <tr><td>NASDAQ OMX</td><td>.0960</td></tr>
    <tr><td>NASDAQ OMX BX</td><td>.03797</td></tr>
    <tr><td>NASDAQ OMX PSX</td><td>.005196</td></tr>
    <tr><td>National</td><td>.002492</td></tr>
    <tr><td>NYSE</td><td>.1824</td></tr>
    <tr><td>NYSE Arca SM</td><td>.07202</td></tr>
    <tr><td>NYSE MMKT</td><td>.00005679</td></tr>
  </tbody>
</table>

Most symbols had similar profiles in exchange market share. [To illustrate, stocks BHP, FE, and XOM were chosen since their volumes were at comparable scales.](http://rcharts.github.io/viewer/?c0e1fc17977fa20a3994)

[Only GOOG had a exchange market share profile which differed somewhat noticeably.](
http://rcharts.github.io/viewer/?1e2ef2392dcfe731ef83) (SLV also had a slight difference, with no NYSE representation.)

[We can also look at the way volumes were spread out over exchanges based on Time of Day.](http://rcharts.github.io/viewer/?ba03ed4250a3839722c5)

## Exchange Volumes and Market Shares Over 2014
The following graphs illustrate the extent of day-to-day consistency for the trends in the last rChart.

With so many exchanges, it may be helpful to amalgamate categories:
![Regular Hours Market Share](https://github.com/TeddyCho/TeddyCho.github.io/blob/master/_posts/img/Regular2014.png)
We see similar exchange market shares for both the opening and closing auctions:
![Opening Auction Market Share](https://github.com/TeddyCho/TeddyCho.github.io/blob/master/_posts/img/Open2014.png)
![Closing Auction Market Share](https://github.com/TeddyCho/TeddyCho.github.io/blob/master/_posts/img/Close2014.png)
After-Hours trading has a different profile for exchange market shares:
![After-Hours Market Share](https://github.com/TeddyCho/TeddyCho.github.io/blob/master/_posts/img/After-Hours2014.png)

## Notes
Some trades had an exchange code "Q", which did not exactly correspond to anything listed in the [spec sheet](www.nyxdata.com/doc/224904). We assumed "Q" referred to the NASDAQ exchange since "T/Q" corresponded to NASDAQ and "T" corresponded to NASDAQ OMX.
