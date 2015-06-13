---
layout: post
title: Where Do Volumes Come From?
unlisted: true
---

# Tasks
> Using NYSE Trades and Quotes (TAQ) data for a representative sample of stocks, find the exchange market shares based on stock, time of day, and date.

# Data
The TAQ data covered the following time frame and symbols:
<table>
  <thead>
    <tr>      <th>Timeframe</th> <th>NASDAQ</th> <th>NYSE</th> <th>NYSEArca</th> <th>NYSEMKT</th>   </tr>
  </thead>
  <tbody>
    <tr>      <td>01-Jan-2014 to 31-Dec-2014</td>
      <td>AMD, GOOG, GT, NDAQ, STLD, TSLA, WFM</td> 
      <td>BAC, BHP, BRKA, CVS, FE, GE, <br/> LTM, LUV, T, WSM, XOM</td> 
      <td>SLV, TBF</td> 
      <td>CCF, LIQT, ONP, ONVO</td> 
    </tr>
  </tbody>
</table>
Transforming the above data (129M rows) to per-day-per-timeOfDay exchange volumes took 991 seconds on a 2.4 GHz/4GB laptop. The raw output from the code is [here](https://github.com/TeddyCho/TAQ/blob/master/data/breakdown5aa0ce4b018e0067.csv).

The exchanges' volumes and market shares for each epoch of each trading day can be found [here](https://github.com/TeddyCho/TAQ/blob/master/data/taskTwo.csv).

# Exchange Market Shares During Regular Trading

When trades are grouped by their symbols' listing exchanges, we observe differences across their exchange market share profiles during regular hours. Notably, exchanges held higher market share for their "home" stocks:

<iframe src = ' https://rawgit.com/TeddyCho/TAQ/master/output/perExchangeForRegular.html ' scrolling='no' frameBorder='0' width="800" height="400"> </iframe>

To further support that listing exchange helps determine exchange market share profile, we expand each group by their constituent symbols.

Within NASDAQ listed stocks, exchange shares were consistent:

<iframe src = ' https://rawgit.com/TeddyCho/TAQ/master/output/NASDAQSymbolsForRegular.html ' scrolling='no' frameBorder='0' width="800" height="400"> </iframe>
 
There was consistency in the exchange market share profiles for NYSE listed stocks, as well:

<iframe src = ' https://rawgit.com/TeddyCho/TAQ/master/output/NYSESymbolsForRegular.html ' scrolling='no' frameBorder='0' width="800" height="400"> </iframe>
 
Consistency was found between our two Arca symbols, save for BATS Y, Direct Edge X, and Chicago:

<iframe src = ' https://rawgit.com/TeddyCho/TAQ/master/output/ArcaSymbolsForRegular.html ' scrolling='no' frameBorder='0' width="800" height="400"> </iframe>
 
 Our NYSEMKT symbols appeared to represent two clusters of exchange market share profiles: one for CCF and ONVO, and one for LIQT and ONP:

<iframe src = ' https://rawgit.com/TeddyCho/TAQ/master/output/NYSEMKTSymbolsForRegular.html ' scrolling='no' frameBorder='0' width="800" height="400"> </iframe>

# Exchange Market Shares During Open and Close Auction

In both the Open and Close epochs, exchange market shares were clearly different based on home exchange. The following graph aggregates stocks by listing exchange and shows volume share for both Open and Close combined:


<iframe src = ' https://rawgit.com/TeddyCho/TAQ/master/output/perExchangeForOpenClose.html ' scrolling='no' frameBorder='0' width="800" height="400"> </iframe>

<!---
# Exchange Market Shares During After-Hours

When grouped by home exchange, we observe stark differences in the exchange share profiles:

<iframe src = ' https://rawgit.com/TeddyCho/TAQ/master/output/perExchangeForAfter-Hours.html ' scrolling='no' frameBorder='0' width="800" height="400"> </iframe>

Among NASDAQ listed stocks, we do see variability in their exchange share profiles for after-hours trading:

<iframe src = ' https://rawgit.com/TeddyCho/TAQ/master/output/NASDAQSymbolsForAfter-Hours.html ' scrolling='no' frameBorder='0' width="800" height="400"> </iframe>
 
 We also see some variability among NYSE listed stocks:

<iframe src = ' https://rawgit.com/TeddyCho/TAQ/master/output/NYSESymbolsForAfter-Hours.html ' scrolling='no' frameBorder='0' width="800" height="400"> </iframe>
 
 Finally, we see some variability among NYSE MKT stocks:

<iframe src = ' https://rawgit.com/TeddyCho/TAQ/master/output/NYSEMKTSymbolsForAfter-Hours.html ' scrolling='no' frameBorder='0' width="800" height="400"> </iframe>
--->

# Exchange Volumes and Market Shares Over 2014
The following graphs illustrate the extent of day-to-day consistency for the trends in the last rChart.

With so many exchanges, it may be helpful to amalgamate categories:
![Regular Hours Market Share](https://raw.githubusercontent.com/TeddyCho/TeddyCho.github.io/master/_posts/img/Regular2014.png)
We see similar exchange market share profiles for both the opening and closing auctions, with an overwhelming showing by NYSE:
![Opening Auction Market Share](https://raw.githubusercontent.com/TeddyCho/TeddyCho.github.io/master/_posts/img/Open2014.png)
![Closing Auction Market Share](https://raw.githubusercontent.com/TeddyCho/TeddyCho.github.io/master/_posts/img/Close2014.png)
After-Hours trading has a different profile for exchange market shares:
![After-Hours Market Share](https://raw.githubusercontent.com/TeddyCho/TeddyCho.github.io/master/_posts/img/After-Hours2014.png)

<!---
# Overall Look at Exchange Market Shares
Over all trades, the volumes were distributed across exhanges as such:

<iframe src = ' https://rawgit.com/TeddyCho/TAQ/master/output/AllStocks.html ' scrolling='no' frameBorder='0' width="800" height="400"> </iframe>

<table>
  <thead>
    <tr><th>Exchange</th><th>Percentage</th></tr>
  </thead>
  <tbody>
    <tr><td>BATS</td><td>6.0629</td></tr>
    <tr><td>BATS Y</td><td>3.2154</td></tr>
    <tr><td>CBOE</td><td>0.0877</td></tr>
    <tr><td>Chicago</td><td>0.5438</td></tr>
    <tr><td>Direct Edge A</td><td>3.2419</td></tr>
    <tr><td>Direct Edge X</td><td>7.8300</td></tr>
    <tr><td>FINRA</td><td>38.6281</td></tr>
    <tr><td>NASDAQ</td><td>3.1614</td></tr>
    <tr><td>NASDAQ OMX</td><td>8.6755</td></tr>
    <tr><td>NASDAQ OMX BX</td><td>3.4933</td></tr>
    <tr><td>NASDAQ OMX PSX</td><td>0.4877</td></tr>
    <tr><td>National</td><td>0.2332</td></tr>
    <tr><td>NYSE</td><td>17.1059</td></tr>
    <tr><td>NYSE Arca SM</td><td>7.1251</td></tr>
    <tr><td>NYSE MMKT</td><td>0.1082</td></tr>
  </tbody>
</table>
--->

# Notes
* A trade's time of day was inferred from Sale Condition as follows:
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

* Some trades had an exchange code "Q", which did not exactly correspond to anything listed in the [spec sheet](www.nyxdata.com/doc/224904). We assumed "Q" referred to the NASDAQ exchange since "T/Q" corresponded to NASDAQ and "T" corresponded to NASDAQ OMX.

* Trades of exchange type "FINRA" are trades which happened off-exchange. Such trades are reported for TAQ publication through FINRA's ADF, TRF, or ORF, as written [here](http://www.finra.org/industry/trade-reporting-faq#100).
