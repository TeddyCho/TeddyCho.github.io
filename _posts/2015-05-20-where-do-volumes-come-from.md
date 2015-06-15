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
    <tr>      <th>Timeframe</th> <th>NASDAQ</th> <th>NYSE</th> <th>Arca</th> <th>NYSEMKT</th>   </tr>
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

## Between Stocks of Different Home Exchange
When trades are grouped by their symbols' listing exchanges, we observe differences across their exchange market share profiles during regular hours. Notably, exchanges held higher market share for their "home" stocks:

<center>
  <button class = "rad-button static light flat">Toggle To Table</button><br/>
<div id="adv_example"></div>
  <div>
    <iframe src = ' https://rawgit.com/TeddyCho/TAQ/master/output/perExchangeForRegular.html ' scrolling='no' frameBorder='0' width="800" height="400"> </iframe>
  </div>
</center>

To further support that listing exchange helps determine exchange market share profile, we expand each group by their constituent symbols.

## NASDAQ Stocks
Within NASDAQ stocks, exchange shares were consistent:

<center><button class = "rad-button static light flat">Toggle To Table</button><br/>
<div id="tablediv2">
<table class="tablesorter">
<tr> <th> Exchange </th> <th> GOOG </th> <th> GT </th> <th> NDAQ </th> <th> STLD </th> <th> TSLA </th> <th> WFM </th>  </tr>
  <tr> <td> BATS </td> <td align="right"> 0.08 </td> <td align="right"> 0.13 </td> <td align="right"> 0.14 </td> <td align="right"> 0.16 </td> <td align="right"> 0.08 </td> <td align="right"> 0.14 </td> </tr>
  <tr> <td> BATS Y </td> <td align="right"> 0.03 </td> <td align="right"> 0.04 </td> <td align="right"> 0.04 </td> <td align="right"> 0.06 </td> <td align="right"> 0.03 </td> <td align="right"> 0.04 </td> </tr>
  <tr> <td> CBOE </td> <td align="right"> 0.00 </td> <td align="right"> 0.00 </td> <td align="right"> 0.00 </td> <td align="right"> 0.00 </td> <td align="right"> 0.00 </td> <td align="right"> 0.00 </td> </tr>
  <tr> <td> Chicago </td> <td align="right"> 0.01 </td> <td align="right"> 0.01 </td> <td align="right"> 0.00 </td> <td align="right"> 0.00 </td> <td align="right"> 0.01 </td> <td align="right"> 0.01 </td> </tr>
  <tr> <td> Direct Edge A </td> <td align="right"> 0.03 </td> <td align="right"> 0.04 </td> <td align="right"> 0.04 </td> <td align="right"> 0.05 </td> <td align="right"> 0.03 </td> <td align="right"> 0.04 </td> </tr>
  <tr> <td> Direct Edge X </td> <td align="right"> 0.13 </td> <td align="right"> 0.10 </td> <td align="right"> 0.08 </td> <td align="right"> 0.08 </td> <td align="right"> 0.25 </td> <td align="right"> 0.12 </td> </tr>
  <tr> <td> NASDAQ </td> <td align="right"> 0.49 </td> <td align="right"> 0.46 </td> <td align="right"> 0.51 </td> <td align="right"> 0.44 </td> <td align="right"> 0.37 </td> <td align="right"> 0.47 </td> </tr>
  <tr> <td> NASDAQ OMX BX </td> <td align="right"> 0.05 </td> <td align="right"> 0.04 </td> <td align="right"> 0.04 </td> <td align="right"> 0.05 </td> <td align="right"> 0.04 </td> <td align="right"> 0.03 </td> </tr>
  <tr> <td> NASDAQ OMX PSX </td> <td align="right"> 0.00 </td> <td align="right"> 0.01 </td> <td align="right"> 0.00 </td> <td align="right"> 0.01 </td> <td align="right"> 0.01 </td> <td align="right"> 0.01 </td> </tr>
  <tr> <td> National </td> <td align="right"> 0.00 </td> <td align="right"> 0.00 </td> <td align="right"> 0.00 </td> <td align="right"> 0.00 </td> <td align="right"> 0.00 </td> <td align="right"> 0.00 </td> </tr>
  <tr> <td> NYSE Arca SM </td> <td align="right"> 0.17 </td> <td align="right"> 0.16 </td> <td align="right"> 0.15 </td> <td align="right"> 0.14 </td> <td align="right"> 0.18 </td> <td align="right"> 0.15 </td> </tr>
  <tr> <td> NYSE MKT </td> <td align="right"> 0.00 </td> <td align="right"> 0.01 </td> <td align="right"> 0.00 </td> <td align="right"> 0.01 </td> <td align="right"> 0.00 </td> <td align="right"> 0.00 </td> </tr>
</table>
</div>
   
<div>
<iframe src = ' https://rawgit.com/TeddyCho/TAQ/master/output/NASDAQSymbolsForRegular.html ' scrolling='no' frameBorder='0' width="800" height="400"> </iframe>
</div>
</center>
 
 ## NYSE Stocks
There was consistency in the exchange market share profiles for NYSE stocks, as well:
<center><button class = "rad-button static light flat">Toggle To Table</button><br/>
<div id="tablediv3">
<table class="tablesorter">
<tr> <th> Exchange </th> <th> AMD </th> <th> BAC </th> <th> BHP </th> <th> BRKA </th> <th> CVS </th> <th> FE </th> <th> GE </th> <th> LTM </th> <th> LUV </th> <th> T </th> <th> WSM </th> <th> XOM </th>  </tr>
  <tr> <td> BATS </td> <td align="right"> 0.11 </td> <td align="right"> 0.10 </td> <td align="right"> 0.14 </td> <td align="right"> 0.40 </td> <td align="right"> 0.10 </td> <td align="right"> 0.14 </td> <td align="right"> 0.11 </td> <td align="right"> 0.09 </td> <td align="right"> 0.15 </td> <td align="right"> 0.12 </td> <td align="right"> 0.08 </td> <td align="right"> 0.12 </td> </tr>
  <tr> <td> BATS Y </td> <td align="right"> 0.05 </td> <td align="right"> 0.07 </td> <td align="right"> 0.03 </td> <td align="right"> 0.03 </td> <td align="right"> 0.03 </td> <td align="right"> 0.04 </td> <td align="right"> 0.07 </td> <td align="right"> 0.03 </td> <td align="right"> 0.05 </td> <td align="right"> 0.06 </td> <td align="right"> 0.04 </td> <td align="right"> 0.03 </td> </tr>
  <tr> <td> CBOE </td> <td align="right"> 0.00 </td> <td align="right"> 0.00 </td> <td align="right"> 0.00 </td> <td align="right"> 0.00 </td> <td align="right"> 0.00 </td> <td align="right"> 0.00 </td> <td align="right"> 0.00 </td> <td align="right"> 0.00 </td> <td align="right"> 0.00 </td> <td align="right"> 0.00 </td> <td align="right"> 0.00 </td> <td align="right"> 0.00 </td> </tr>
  <tr> <td> Chicago </td> <td align="right"> 0.01 </td> <td align="right"> 0.01 </td> <td align="right"> 0.01 </td> <td align="right"> 0.00 </td> <td align="right"> 0.00 </td> <td align="right"> 0.00 </td> <td align="right"> 0.01 </td> <td align="right"> 0.01 </td> <td align="right"> 0.00 </td> <td align="right"> 0.01 </td> <td align="right"> 0.00 </td> <td align="right"> 0.01 </td> </tr>
  <tr> <td> Direct Edge A </td> <td align="right"> 0.06 </td> <td align="right"> 0.07 </td> <td align="right"> 0.05 </td> <td align="right"> 0.01 </td> <td align="right"> 0.05 </td> <td align="right"> 0.04 </td> <td align="right"> 0.07 </td> <td align="right"> 0.03 </td> <td align="right"> 0.04 </td> <td align="right"> 0.05 </td> <td align="right"> 0.03 </td> <td align="right"> 0.03 </td> </tr>
  <tr> <td> Direct Edge X </td> <td align="right"> 0.17 </td> <td align="right"> 0.16 </td> <td align="right"> 0.08 </td> <td align="right"> 0.04 </td> <td align="right"> 0.09 </td> <td align="right"> 0.08 </td> <td align="right"> 0.12 </td> <td align="right"> 0.10 </td> <td align="right"> 0.10 </td> <td align="right"> 0.11 </td> <td align="right"> 0.10 </td> <td align="right"> 0.08 </td> </tr>
  <tr> <td> NASDAQ OMX </td> <td align="right"> 0.14 </td> <td align="right"> 0.15 </td> <td align="right"> 0.18 </td> <td align="right"> 0.21 </td> <td align="right"> 0.27 </td> <td align="right"> 0.26 </td> <td align="right"> 0.17 </td> <td align="right"> 0.23 </td> <td align="right"> 0.24 </td> <td align="right"> 0.21 </td> <td align="right"> 0.25 </td> <td align="right"> 0.27 </td> </tr>
  <tr> <td> NASDAQ OMX BX </td> <td align="right"> 0.06 </td> <td align="right"> 0.08 </td> <td align="right"> 0.03 </td> <td align="right"> 0.01 </td> <td align="right"> 0.04 </td> <td align="right"> 0.04 </td> <td align="right"> 0.08 </td> <td align="right"> 0.04 </td> <td align="right"> 0.05 </td> <td align="right"> 0.06 </td> <td align="right"> 0.04 </td> <td align="right"> 0.03 </td> </tr>
  <tr> <td> NASDAQ OMX PSX </td> <td align="right"> 0.01 </td> <td align="right"> 0.01 </td> <td align="right"> 0.01 </td> <td align="right"> 0.00 </td> <td align="right"> 0.01 </td> <td align="right"> 0.00 </td> <td align="right"> 0.01 </td> <td align="right"> 0.01 </td> <td align="right"> 0.01 </td> <td align="right"> 0.01 </td> <td align="right"> 0.01 </td> <td align="right"> 0.01 </td> </tr>
  <tr> <td> National </td> <td align="right"> 0.01 </td> <td align="right"> 0.01 </td> <td align="right"> 0.00 </td> <td align="right"> 0.01 </td> <td align="right"> 0.00 </td> <td align="right"> 0.00 </td> <td align="right"> 0.00 </td> <td align="right"> 0.00 </td> <td align="right"> 0.00 </td> <td align="right"> 0.00 </td> <td align="right"> 0.00 </td> <td align="right"> 0.00 </td> </tr>
  <tr> <td> NYSE </td> <td align="right"> 0.27 </td> <td align="right"> 0.23 </td> <td align="right"> 0.34 </td> <td align="right"> 0.29 </td> <td align="right"> 0.30 </td> <td align="right"> 0.28 </td> <td align="right"> 0.27 </td> <td align="right"> 0.28 </td> <td align="right"> 0.23 </td> <td align="right"> 0.25 </td> <td align="right"> 0.24 </td> <td align="right"> 0.26 </td> </tr>
  <tr> <td> NYSE Arca SM </td> <td align="right"> 0.11 </td> <td align="right"> 0.11 </td> <td align="right"> 0.14 </td> <td align="right"> 0.00 </td> <td align="right"> 0.12 </td> <td align="right"> 0.11 </td> <td align="right"> 0.10 </td> <td align="right"> 0.18 </td> <td align="right"> 0.11 </td> <td align="right"> 0.12 </td> <td align="right"> 0.19 </td> <td align="right"> 0.16 </td> </tr>
   </table>
</div>
<div>
<iframe src = ' https://rawgit.com/TeddyCho/TAQ/master/output/NYSESymbolsForRegular.html ' scrolling='no' frameBorder='0' width="800" height="400"> </iframe>
</div>
</center>
 
## Arca Stocks
Consistency was found between our two Arca symbols, save for BATS Y, Direct Edge X, and Chicago:

<center><button class = "rad-button static light flat">Toggle To Table</button><br/>
<div id="tablediv4">
<table class="tablesorter">
<tr> <th> Exchange </th> <th> SLV </th> <th> TBF </th>  </tr>
  <tr> <td> BATS </td> <td align="right"> 0.14 </td> <td align="right"> 0.14 </td> </tr>
  <tr> <td> BATS Y </td> <td align="right"> 0.07 </td> <td align="right"> 0.05 </td> </tr>
  <tr> <td> CBOE </td> <td align="right"> 0.00 </td> <td align="right"> 0.00 </td> </tr>
  <tr> <td> Chicago </td> <td align="right"> 0.02 </td> <td align="right"> 0.00 </td> </tr>
  <tr> <td> Direct Edge A </td> <td align="right"> 0.08 </td> <td align="right"> 0.08 </td> </tr>
  <tr> <td> Direct Edge X </td> <td align="right"> 0.14 </td> <td align="right"> 0.23 </td> </tr>
  <tr> <td> NASDAQ OMX </td> <td align="right"> 0.18 </td> <td align="right"> 0.17 </td> </tr>
  <tr> <td> NASDAQ OMX BX </td> <td align="right"> 0.08 </td> <td align="right"> 0.07 </td> </tr>
  <tr> <td> NASDAQ OMX PSX </td> <td align="right"> 0.02 </td> <td align="right"> 0.02 </td> </tr>
  <tr> <td> National </td> <td align="right"> 0.00 </td> <td align="right"> 0.00 </td> </tr>
  <tr> <td> NYSE Arca SM </td> <td align="right"> 0.26 </td> <td align="right"> 0.24 </td> </tr>
  <tr> <td> NYSE MKT </td> <td align="right"> 0.00 </td> <td align="right"> 0.00 </td> </tr>
   </table>
</div>
<div>
<iframe src = ' https://rawgit.com/TeddyCho/TAQ/master/output/ArcaSymbolsForRegular.html ' scrolling='no' frameBorder='0' width="800" height="400"> </iframe>
</div>
</center>

## NYSEMKT Stocks 
Our NYSEMKT symbols appeared to represent two clusters of exchange market share profiles: one for CCF and ONVO, and one for LIQT and ONP:

<center><button class = "rad-button static light flat">Toggle To Table</button><br/>
<div id="tablediv5">
<table class="tablesorter">
<tr> <th> Exchange </th> <th> SLV </th> <th> TBF </th>  </tr>
  <tr> <td> BATS </td> <td align="right"> 0.14 </td> <td align="right"> 0.14 </td> </tr>
  <tr> <td> BATS Y </td> <td align="right"> 0.07 </td> <td align="right"> 0.05 </td> </tr>
  <tr> <td> CBOE </td> <td align="right"> 0.00 </td> <td align="right"> 0.00 </td> </tr>
  <tr> <td> Chicago </td> <td align="right"> 0.02 </td> <td align="right"> 0.00 </td> </tr>
  <tr> <td> Direct Edge A </td> <td align="right"> 0.08 </td> <td align="right"> 0.08 </td> </tr>
  <tr> <td> Direct Edge X </td> <td align="right"> 0.14 </td> <td align="right"> 0.23 </td> </tr>
  <tr> <td> NASDAQ OMX </td> <td align="right"> 0.18 </td> <td align="right"> 0.17 </td> </tr>
  <tr> <td> NASDAQ OMX BX </td> <td align="right"> 0.08 </td> <td align="right"> 0.07 </td> </tr>
  <tr> <td> NASDAQ OMX PSX </td> <td align="right"> 0.02 </td> <td align="right"> 0.02 </td> </tr>
  <tr> <td> National </td> <td align="right"> 0.00 </td> <td align="right"> 0.00 </td> </tr>
  <tr> <td> NYSE Arca SM </td> <td align="right"> 0.26 </td> <td align="right"> 0.24 </td> </tr>
  <tr> <td> NYSE MKT </td> <td align="right"> 0.00 </td> <td align="right"> 0.00 </td> </tr>
   </table>
</div>
<div>
<iframe src = ' https://rawgit.com/TeddyCho/TAQ/master/output/NYSEMKTSymbolsForRegular.html ' scrolling='no' frameBorder='0' width="800" height="400"> </iframe>
</div>
</center>

# Exchange Market Shares During Open and Close Auction

In both the Open and Close epochs, exchange market shares were clearly different based on home exchange. The following graph aggregates stocks by listing exchange and shows volume share for both Open and Close combined:

<center><button class = "rad-button static light flat">Toggle To Table</button><br/>
<div id="tablediv6">
<table class="tablesorter">
<tr> <th> Exchange </th> <th> Arca </th> <th> NASDAQ </th> <th> NYSE </th> <th> NYSEMKT </th>  </tr>
  <tr> <td> BATS </td> <td align="right"> 0.14 </td> <td align="right"> 0.12 </td> <td align="right"> 0.11 </td> <td align="right"> 0.06 </td> </tr>
  <tr> <td> BATS Y </td> <td align="right"> 0.07 </td> <td align="right"> 0.04 </td> <td align="right"> 0.06 </td> <td align="right"> 0.03 </td> </tr>
  <tr> <td> CBOE </td> <td align="right"> 0.00 </td> <td align="right"> 0.00 </td> <td align="right"> 0.00 </td> <td align="right"> 0.00 </td> </tr>
  <tr> <td> Chicago </td> <td align="right"> 0.02 </td> <td align="right"> 0.01 </td> <td align="right"> 0.01 </td> <td align="right"> 0.01 </td> </tr>
  <tr> <td> Direct Edge A </td> <td align="right"> 0.08 </td> <td align="right"> 0.04 </td> <td align="right"> 0.06 </td> <td align="right"> 0.03 </td> </tr>
  <tr> <td> Direct Edge X </td> <td align="right"> 0.14 </td> <td align="right"> 0.15 </td> <td align="right"> 0.14 </td> <td align="right"> 0.32 </td> </tr>
  <tr> <td> NASDAQ </td> <td align="right"> 0.00 </td> <td align="right"> 0.44 </td> <td align="right"> 0.00 </td> <td align="right"> 0.00 </td> </tr>
  <tr> <td> NASDAQ OMX </td> <td align="right"> 0.18 </td> <td align="right"> 0.00 </td> <td align="right"> 0.18 </td> <td align="right"> 0.19 </td> </tr>
  <tr> <td> NASDAQ OMX BX </td> <td align="right"> 0.08 </td> <td align="right"> 0.04 </td> <td align="right"> 0.07 </td> <td align="right"> 0.02 </td> </tr>
  <tr> <td> NASDAQ OMX PSX </td> <td align="right"> 0.02 </td> <td align="right"> 0.01 </td> <td align="right"> 0.01 </td> <td align="right"> 0.00 </td> </tr>
  <tr> <td> National </td> <td align="right"> 0.00 </td> <td align="right"> 0.00 </td> <td align="right"> 0.00 </td> <td align="right"> 0.02 </td> </tr>
  <tr> <td> NYSE </td> <td align="right"> 0.00 </td> <td align="right"> 0.00 </td> <td align="right"> 0.25 </td> <td align="right"> 0.00 </td> </tr>
  <tr> <td> NYSE Arca SM </td> <td align="right"> 0.26 </td> <td align="right"> 0.16 </td> <td align="right"> 0.11 </td> <td align="right"> 0.18 </td> </tr>
  <tr> <td> NYSE MKT </td> <td align="right"> 0.00 </td> <td align="right"> 0.00 </td> <td align="right"> 0.00 </td> <td align="right"> 0.14 </td> </tr>
   </table>
</div>
<div>
<iframe src = ' https://rawgit.com/TeddyCho/TAQ/master/output/perExchangeForOpenClose.html ' scrolling='no' frameBorder='0' width="800" height="400"> </iframe>
</div>
</center>

# Exchange Share over different Trade Group Sizes
<div id="slides">
    <img src="http://placehold.it/940x528">
    <img src="http://legdays.com/wp-content/uploads/2015/02/IMG_7319-e1425057350827-1024x248.jpg">
    <img src="http://legdays.com/wp-content/uploads/2015/02/FullSizeRender_2-e1424272121118-1024x255.jpg">
</div>

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

* Trades of exchange type "FINRA" are trades which happened off-exchange. Such trades are reported for TAQ publication through FINRA's ADF, TRF, or ORF, as written [here](http://www.finra.org/industry/trade-reporting-faq#100). <strong>These trades are excluded from the analysis.</strong>

<script>
$(function(){
  $('#tablediv1').hide();
  $('#tablediv2').hide();
  $('#tablediv3').hide();
  $('#tablediv4').hide();
  $('#tablediv5').hide();
  $('#tablediv6').hide();
  $('button').click(function() {
    $(this).next().next().fadeToggle("fast");
    $(this).next().next().next().fadeToggle("fast");
    if ($(this).text() == 'Toggle to Chart') {
      $(this).text('Toggle to Table');
    } else {
      $(this).text('Toggle to Chart');
    }
  });
  $("#slides").slidesjs({
      width: 300, height: 200,
        navigation: {
          effect: "fade"
        },
        pagination: {
          effect: "fade"
        },
        effect: {
          fade: {
            speed: 100
          }
        },
        navigation: false
    });
});
$(document).ready(function () {

  var container = document.getElementById('adv_example');
  var percentRenderer = function (instance, td, row, col, prop, value, cellProperties) {
    Handsontable.renderers.NumericRenderer.apply(this, arguments);
    td.style.color = (value < 0) ? 'red' : 'green';
  };
  
  var advancedData = [
    ["Afghanistan","30.552","1000s","2013","0.0244","27.708","24.019","11.215"],
    ["Albania","2.774","1000s","2013","-0.0100","2.884","3.015","3.228"],
    ["Algeria","39.208","1000s","2013","0.0189","36.383","33.461","25.577"],
    ["Angola","21.472","1000s","2013","0.0313","18.927","15.977","10.051"],
    ["Antigua and Barbuda","90","1000s","2013","0.0103","86","82","62"],
    ["Argentina","41.446","1000s","2013","0.0087","40.024","38.309","32.17"],
    ["Armenia","2.977","1000s","2013","0.025","2.968","3.026","3.543"],
    ["Australia","23.131","1000s","2013","0.0179","21.692","20.127","16.814"],
    ["Austria","8.474","1000s","2013","0.0052","8.365","8.172","7.62"],
    ["Azerbaijan","9.296","1000s","2012","0.0134","8.763","8.234","6.994"],
    ["Bahrain","1.332","1000s","2013","0.0109","1.192","821","481"],
    ["Bangladesh","156.595","1000s","2013","0.0123","149.503","141.235","104.779"],
    ["Barbados","285","1000s","2013","0.0050","279","272","258"],
    ["Belarus","9.464","1000s","2012","-0.0010","9.528","9.797","10.14"],
    ["Belgium","11.195","1000s","2013","0.0060","10.796","10.421","9.938"],
    ["Belize","324","1000s","2012","0.0246","294","258","179"],
    ["Benin","10.323","1000s","2013","0.0271","9.241","7.923","4.836"],
    ["Bhutan","754","1000s","2013","0.0163","705","634","530"],
    ["Bolivia","10.671","1000s","2013","0.0167","9.993","9.188","6.636"],
    ["Bosnia and Herzegovina","3.829","1000s","2013","-0.0012","3.853","3.887","4.585"],
    ["Botswana","2.021","1000s","2013","0.0086","1.952","1.855","1.343"],
    ["Brazil","200.362","1000s","2013","0.0086","193.491","184.01","147.079"],
    ["Brunei","418","1000s","2013","0.0135","394","361","250"],
    ["Bulgaria","7.265","1000s","2013","-0.0056","7.444","7.781","8.877"],
    ["Burkina Faso","16.935","1000s","2013","0.0288","15.095","13.034","8.58"],
    ["Burundi","10.163","1000s","2013","0.0318","8.927","7.511","5.449"],
    ["Cambodia","15.135","1000s","2013","0.0182","14.144","13.149","8.769"],
    ["Cameroon","22.254","1000s","2013","0.0255","20.104","17.675","11.717"],
    ["Canada","35.158","1000s","2013","0.0116","33.629","31.995","27.379"],
    ["Cape Verde","499","1000s","2013","0.0091","486","474","346"],
    ["Central African Republic","4.616","1000s","2013","0.0202","4.266","3.894","2.852"],
    ["Chad","12.825","1000s","2013","0.0303","11.371","9.665","5.765"],
    ["Chile","17.62","1000s","2013","0.0089","16.992","16.168","12.981"],
    ["China","1.357.380","1000s","2013","0.0049","1.331.260","1.296.075","1.118.650"],
    ["Colombia","48.321","1000s","2013","0.0129","45.803","42.528","32.657"],
    ["Comoros","718","1000s","2012","0.0247","649","570","393"],
    ["Congo","67.514","1000s","2013","0.0275","60.486","52.487","33.728"],
    ["Congo-Brazzaville","4.448","1000s","2013","0.0255","3.995","3.449","2.32"],
    ["Costa Rica","4.872","1000s","2013","0.0139","4.601","4.246","3.001"],
    ["Croatia","4.253","1000s","2013","-0.0035","4.429","4.439","4.767"],
    ["Cuba","11.266","1000s","2013","-0.0005","11.289","11.273","10.504"],
    ["Cyprus","1.141","1000s","2013","0.0108","1.091","1.016","751"],
    ["Czech Republic","10.521","1000s","2013","0.0010","10.444","10.197","10.361"],
    ["Denmark","5.614","1000s","2013","0.0040","5.523","5.405","5.133"],
    ["Djibouti","873","1000s","2013","0.0154","822","766","560"],
    ["Dominica","72","1000s","2013","0.0045","71","70","71"],
    ["Dominican Republic","10.404","1000s","2013","0.0124","9.884","9.207","7.099"],
    ["Ecuador","15.492","1000s","2012","0.0161","14.512","13.28","9.651"],
    ["Egypt","82.056","1000s","2013","0.0165","76.775","70.591","55.207"],
    ["El Salvador","6.34","1000s","2013","0.0068","6.183","6.05","5.269"],
    ["Equatorial Guinea","757","1000s","2013","0.0281","677","586","362"],
    ["Eritrea","6.333","1000s","2013","0.0330","5.558","4.666","3.21"],
    ["Estonia","1.325","1000s","2013","-0.0003","1.335","1.363","1.568"],
    ["Ethiopia","94.101","1000s","2013","0.0259","84.838","74.066","46.435"],
    ["Fiji","881","1000s","2013","0.0072","852","819","724"],
    ["Finland","5.439","1000s","2013","0.0047","5.339","5.228","4.964"],
    ["France","66.028","1000s","2013","0.0054","64.703","62.702","58.114"],
    ["Gabon","1.672","1000s","2013","0.0240","1.519","1.347","921"],
    ["Gambia","1.849","1000s","2013","0.0324","1.628","1.392","881"],
    ["Georgia","4.477","1000s","2013","-0.0031","4.411","4.318","4.803"],
    ["Germany","80.622","1000s","2013","0.0024","81.902","82.516","78.751"],
    ["Ghana","25.905","1000s","2013","0.0212","23.692","20.836","14.233"],
    ["Greece","11.032","1000s","2013","-0.0054","11.187","11.056","10.089"],
    ["Grenada","106","1000s","2013","0.0039","104","103","97"],
    ["Guatemala","15.468","1000s","2013","0.0256","13.989","12.368","8.688"],
    ["Guinea","11.745","1000s","2013","2.57","10.593","9.38","5.751"],
    ["Guinea-Bissau","1.704","1000s","2013","0.0245","1.551","1.391","995"],
    ["Guyana","800","1000s","2013","0.0053","781","757","728"],
    ["Haiti","10.317","1000s","2013","0.0141","9.765","9.13","6.965"],
    ["Honduras","8.098","1000s","2013","0.0204","7.47","6.762","4.767"],
    ["Hong Kong","7.188","1000s","2013","0.0046","6.973","6.784","5.686"],
    ["Hungary","9.897","1000s","2013","-0.0023","10.023","10.107","10.482"],
    ["Iceland","323","1000s","2013","0.0071","318","292","253"],
    ["India","1.252.140","1000s","2013","0.0125","1.190.138","1.110.626","851.375"],
    ["Indonesia","249.866","1000s","2013","0.0122","237.487","221.294","175.461"],
    ["Iran","77.447","1000s","2013","0.0134","73.543","69.342","54.938"],
    ["Iraq","33.417","1000s","2013","0.0258","30.163","26.674","17.074"],
    ["Ireland","4.595","1000s","2013","0.0018","4.535","4.07","3.511"],
    ["Israel","8.059","1000s","2013","0.0188","7.486","6.809","4.518"],
    ["Italy","59.831","1000s","2013","0.0049","59.095","57.685","56.672"],
    ["Ivory Coast","20.316","1000s","2013","0.0240","18.601","17.144","11.711"],
    ["Jamaica","2.715","1000s","2013","0.0027","2.681","2.634","2.375"],
    ["Japan","127.339","1000s","2013","-0.0017","127.558","127.761","123.116"],
    ["Jordan","6.459","1000s","2013","0.0223","5.915","5.29","3.056"],
    ["Kazakhstan","17.038","1000s","2013","0.0147","16.093","15.013","16.25"],
    ["Kenya","44.354","1000s","2013","0.0272","39.825","34.835","22.667"],
    ["Kiribati","102","1000s","2013","0.0155","96","89","69"],
    ["Kosovo","1.824","1000s","2013","0.0093","1.761","1.705","1.827"],
    ["Kuwait","3.369","1000s","2013","0.0363","2.85","2.196","2.059"],
    ["Kyrgyzstan","5.72","1000s","2013","0.0200","5.383","5.105","4.308"],
    ["Laos","6.77","1000s","2013","0.0186","6.268","5.699","4.123"],
    ["Latvia","2.013","1000s","2013","-0.0103","2.142","2.263","2.667"],
    ["Lebanon","4.467","1000s","2013","0.0096","4.247","3.854","2.677"],
    ["Lesotho","2.074","1000s","2013","0.0112","1.99","1.912","1.57"],
    ["Liberia","4.294","1000s","2013","0.0247","3.821","3.185","2.137"],
    ["Libya","6.202","1000s","2013","0.0076","5.964","5.507","4.161"],
    ["Lithuania","2.956","1000s","2013","-0.0106","3.163","3.377","3.684"],
    ["Luxembourg","543","1000s","2013","0.0231","498","458","377"],
    ["Macedonia","2.107","1000s","2013","0.0008","2.101","2.086","2.006"],
    ["Madagascar","22.925","1000s","2013","0.0283","20.496","17.763","11.206"],
    ["Malawi","16.363","1000s","2013","0.0287","14.573","12.569","9.105"],
    ["Malaysia","29.717","1000s","2013","0.0163","27.79","25.365","17.707"],
    ["Maldives","345","1000s","2013","0.0194","320","293","210"],
    ["Mali","15.302","1000s","2013","0.0302","13.559","11.573","7.826"],
    ["Malta","423","1000s","2013","0.0091","412","401","351"],
    ["Mauritania","3.89","1000s","2013","0.0247","3.516","3.055","1.969"],
    ["Mauritius","1.296","1000s","2013","0.0040","1.275","1.233","1.049"],
    ["Mexico","122.332","1000s","2013","0.0123","116.423","109.382","84.327"],
    ["Moldova","3.559","1000s","2013","-0.0001","3.566","3.604","3.681"],
    ["Mongolia","2.839","1000s","2013","0.0152","2.672","2.496","2.141"],
    ["Montenegro","621","1000s","2013","0.0005","619","615","612"],
    ["Morocco","33.008","1000s","2013","0.0150","31.277","29.856","24.212"],
    ["Mozambique","25.834","1000s","2013","0.0250","23.361","20.439","13.395"],
    ["Myanmar","53.259","1000s","2013","0.0087","51.54","49.875","41.445"],
    ["Namibia","2.303","1000s","2013","0.0194","2.143","2.003","1.361"],
    ["Nepal","27.797","1000s","2013","0.0118","26.545","24.922","17.68"],
    ["Netherlands","16.804","1000s","2013","0.0029","16.53","16.282","14.849"],
    ["New Zealand","4.471","1000s","2013","0.0085","4.316","4.088","3.299"],
    ["Nicaragua","6.08","1000s","2013","0.0148","5.743","5.386","4.046"],
    ["Niger","17.831","1000s","2013","0.0393","15.303","12.709","7.52"],
    ["Nigeria","173.615","1000s","2013","0.0283","155.381","135.999","93.18"],
    ["North Korea","24.895","1000s","2013","0.0053","24.372","23.639","19.895"],
    ["Norway","5.084","1000s","2013","0.0131","4.829","4.592","4.227"],
    ["Oman","3.632","1000s","2013","0.0961","2.663","2.464","1.743"],
    ["Pakistan","182.143","1000s","2013","0.0166","170.094","155.151","107.865"],
    ["Panama","3.864","1000s","2013","0.0163","3.616","3.303","2.435"],
    ["Papua New Guinea","7.321","1000s","2013","0.0215","6.705","5.948","4.057"],
    ["Paraguay","6.802","1000s","2013","0.0172","6.347","5.793","4.139"],
    ["Peru","30.376","1000s","2013","0.0129","28.934","27.404","21.326"],
    ["Philippines","98.394","1000s","2013","0.0174","91.886","84.231","60.41"],
    ["Poland","38.531","1000s","2013","-0.0001","38.152","38.182","37.962"],
    ["Portugal","10.46","1000s","2013","-0.0052","10.568","10.484","10.005"],
    ["Qatar","2.169","1000s","2013","0.0576","1.564","720","463"],
    ["Romania","19.964","1000s","2013","-0.0056","20.367","21.452","23.161"],
    ["Russia","143.5","1000s","2013","0.0022","141.909","143.821","147.721"],
    ["Rwanda","11.777","1000s","2013","0.0278","10.53","9.254","7.224"],
    ["Saint Kitts and Nevis","54","1000s","2013","0.0113","52","48","41"],
    ["Saint Lucia","182","1000s","2013","0.0078","175","163","136"],
    ["Saint Vincent and the Grenadines","109","1000s","2013","0.0000","109","109","107"],
    ["Samoa","190","1000s","2013","0.0079","185","179","162"],
    ["San Marino","31","1000s","2013","0.0064","31","29","24"],
    ["Sao Tome and Principe","193","1000s","2013","0.0260","173","151","115"],
    ["Saudi Arabia","28.829","1000s","2013","0.0191","26.796","23.839","15.665"],
    ["Senegal","14.133","1000s","2013","0.0297","12.587","10.968","7.285"],
    ["Serbia","7.164","1000s","2013","-0.0049","7.321","7.463","n.a."],
    ["Seychelles","89","1000s","2013","0.0099","87","82","69"],
    ["Sierra Leone","6.092","1000s","2013","0.0190","5.641","4.928","3.993"],
    ["Singapore","5.399","1000s","2013","0.0163","4.988","4.167","2.931"],
    ["Slovak Republic","5.414","1000s","2013","0.0012","5.386","5.372","5.276"],
    ["Slovenia","2.06","1000s","2013","0.0016","2.04","1.997","1.996"],
    ["Solomon Islands","561","1000s","2013","0.0212","515","458","303"],
    ["Somalia","10.496","1000s","2013","0.0295","9.381","8.25","6.285"],
    ["South Africa","52.982","1000s","2013","0.0135","50.223","47.019","34.491"],
    ["South Korea","50.22","1000s","2013","0.0043","49.182","48.039","42.449"],
    ["South Sudan","11.296","1000s","2013","0.0423","9.521","7.73","5.775"],
    ["Spain","46.647","1000s","2013","-0.0024","46.363","42.922","38.791"],
    ["Sri Lanka","20.483","1000s","2013","0.0076","20.45","19.435","16.825"],
    ["Sudan","37.964","1000s","2013","0.0207","34.853","30.779","19.295"],
    ["Suriname","539","1000s","2013","0.0089","520","493","400"],
    ["Swaziland","1.25","1000s","2013","0.0151","1.174","1.095","834"],
    ["Sweden","9.593","1000s","2013","0.0077","9.299","8.994","8.493"],
    ["Switzerland","8.081","1000s","2013","0.0106","7.744","7.39","6.647"],
    ["Syria","22.846","1000s","2013","0.0199","21.032","17.676","12.088"],
    ["Tajikistan","8.208","1000s","2013","0.0248","7.447","6.664","5.16"],
    ["Tanzania","49.253","1000s","2013","0.0308","43.64","37.765","24.686"],
    ["Thailand","67.011","1000s","2013","0.0034","66.277","65.087","55.833"],
    ["The Bahamas","377","1000s","2013","0.0146","354","322","252"],
    ["Timor-Leste","1.178","1000s","2013","0.0255","1.049","967","730"],
    ["Togo","6.817","1000s","2013","0.0262","6.144","5.398","3.685"],
    ["Tonga","105","1000s","2013","0.0036","104","100","95"],
    ["Trinidad and Tobago","1.341","1000s","2013","0.0028","1.323","1.29","1.214"],
    ["Tunisia","10.886","1000s","2013","0.0101","10.44","9.932","7.959"],
    ["Turkey","74.933","1000s","2013","0.0126","71.241","66.846","53.066"],
    ["Turkmenistan","5.24","1000s","2013","0.0130","4.979","4.697","3.571"],
    ["Tuvalu","10","1000s","2013","0.0016","10","10","9"],
    ["UAE","9.346","1000s","2013","0.0153","7.718","3.659","1.707"],
    ["Uganda","37.579","1000s","2013","0.0339","32.864","27.767","16.923"],
    ["UK","64.097","1000s","2013","0.0063","62.276","59.988","57.077"],
    ["Ukraine","45.49","1000s","2013","-0.0023","46.053","47.452","51.773"],
    ["Uruguay","3.407","1000s","2013","0.0035","3.36","3.324","3.089"],
    ["USA","316.129","1000s","2013","0.0072","306.772","292.805","246.819"],
    ["Uzbekistan","30.241","1000s","2013","0.0157","27.767","25.864","20.077"],
    ["Vanuatu","253","1000s","2013","0.0222","231","204","143"],
    ["Venezuela","30.405","1000s","2013","0.0150","28.583","26.261","19.256"],
    ["Vietnam","89.709","1000s","2013","0.0105","86.025","81.438","64.774"],
    ["Yemen","24.407","1000s","2013","0.0233","22.23","19.613","11.27"],
    ["Zambia","14.539","1000s","2013","0.0329","12.825","11.175","7.647"],
    ["Zimbabwe","14.15","1000s","2013","0.0310","12.889","12.693","10.167"],
    ["Zimbabwe","14.15","1000s","2013","0.0310","12.889","12.693","10.167"]
  ];
  
  var hot = new Handsontable(container, {
    data: advancedData,
    height: 396,
    colHeaders: ["Country", "Level", "Units", "As Of", "1Y Chg", "5Y Ago", "10Y Ago", "25Y Ago"],
    rowHeaders: true,
    stretchH: 'all',
    columnSorting: true,
    contextMenu: true,
    className: "htCenter htMiddle",
    readOnly: true,
    columns: [
      {data: 0, type: 'text'},
      {data: 1, type: 'numeric', format: '0,0.00[0000]'},
      {data: 2, type: 'text'},
      {data: 3, type: 'numeric', format: '0'},
      {data: 4, type: 'numeric', format: '0.00%', renderer: percentRenderer},
      {data: 5, type: 'numeric', format: '0,0.00[0000]'},
      {data: 6, type: 'numeric', format: '0,0.00[0000]'}
    ]
  });
  
});
</script>

