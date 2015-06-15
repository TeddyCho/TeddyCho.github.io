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
  $('#adv_example').hide();
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
    ["Laos","6.77","1000s","2013","0.0186","6.268","5.699","4.123"],
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

