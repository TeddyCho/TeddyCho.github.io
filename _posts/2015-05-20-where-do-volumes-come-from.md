---
layout: post
title: Where Do Volumes Come From?
unlisted: true
---
<style>
    
    .slidesjs-pagination {
      margin: 6px 0 0;
      float: right;
      list-style: none;
    }

    .slidesjs-pagination li {
      float: left;
      margin: 0 1px;
    }

    .slidesjs-pagination li a {
      display: block;
      width: 13px;
      height: 0;
      padding-top: 13px;
      background-image: url(/img/pagination.png);
      background-position: 0 0;
      float: left;
      overflow: hidden;
    }

    .navbar {
      overflow: hidden
    }
  </style>
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
<!---
Transforming the above data (129M rows) to per-day-per-timeOfDay exchange volumes took 991 seconds on a 2.4 GHz/4GB laptop. The raw output from the code is [here](https://github.com/TeddyCho/TAQ/blob/master/data/breakdown5aa0ce4b018e0067.csv).

The exchanges' volumes and market shares for each epoch of each trading day can be found [here](https://github.com/TeddyCho/TAQ/blob/master/data/taskTwo.csv).
--->

# Exchange Profiles
<table>
  <thead>
    <tr><th>Exchange</th> <th>Fee Structure</th> <th>Profile</th> </tr>
  </thead>
  <tbody>
    <tr bgcolor="#FFB599"><td>NYSE</td><td>Maker/Taker</td><td>Largest stock exchange by volume, geared for trading stock in medium and large cap companies. Features a physical trading floor.  Owned by Intercontinental Exchange (ICE).</td></tr>
    <tr bgcolor="#FFB599"><td>NYSE Arca</td><td>Maker/Taker</td><td>ICE's fully electronic exchange.</td></tr>
    <tr bgcolor="#FFB599"><td>NYSE MKT</td><td>Maker/Taker</td><td>ICE's exchange for small-cap companies following the NYSE exchange model.</td></tr>
    <tr bgcolor="#FFCE96"><td>NASDAQ</td><td>Maker/Taker</td><td>Second largest stock exchange by volume.</td></tr>
    <tr bgcolor="#FFCE96"><td>NASDAQ OMX BX</td><td><a href="http://www.nasdaqtrader.com/Trader.aspx?id=bx_pricing">Taker/Maker</a></td><td>NASDAQ's alternative exchange offering rebates for taking liquidity.</td></tr>
    <tr bgcolor="#FFCE96"><td>NASDAQ PSX</td><td>Maker/Taker</td><td>NASDAQ's alternative exchange offering pro rata allocation.</td></tr>
    <tr bgcolor="#FFF59A"><td>BATS BZX</td><td>Maker/Taker</td><td>BATS's flagship electronic exchange.</td></tr>
    <tr bgcolor="#FFF59A"><td>BATS BYX</td><td><a href="https://batstrading.com/resources/regulation/rule_book/BYX_Fee_Schedule.pdf">Taker/Maker</a></td><td>BATS's alternative electronic exchange offering rebates for taking liquidity.</td></tr>
    <tr bgcolor="#FFF59A"><td>BATS EDGA</td><td>Maker/Taker</td><td>BATS's alternative electronic exchange .</td></tr>
    <tr bgcolor="#FFF59A"><td>BATS EDGX</td><td><a href="http://www.batsglobalmarkets.com/us/equities/membership/fee_schedule/edga/">Taker/Maker</a></td><td>BATS's alternative electronic exchange offering rebates for.</td></tr>
    <tr bgcolor="#CBFF8A"><td>CHX</td><td>Maker/Taker</td><td>Fully electronic exchange, with market share < 1%. The only current exchange not owned by BATS, ICE, or NASDAQ.</td></tr>
    <tr bgcolor="#C2F7F1"><td>CBSX</td><td><a href="http://www.cboe.com/publish/cbsxfeeschedule/cbsxfeeschedule.pdf">Neutral</a></td><td>CBOE's electronic stock exchange, which was <a href="http://www.bloomberg.com/news/articles/2014-05-02/national-stock-exchange-files-with-sec-to-halt-operations">closed in April 2014</a>.</td></tr>
    <tr bgcolor="#D3B5E3"><td>NSX</td><td><a href="http://www.nsx.com/images/documents/bylaws/FeeSchedule04152014.pdf">Taker/Maker</a></td><td>Electronic exchange which <a href="http://www.reuters.com/article/2015/02/13/us-nationalstockexchange-cboe-holdings-idUSKBN0LH2BF20150213">closed in May 2014</a>. Undergoing actions <a href="http://www.nsx.com/index.php/news-views/376-expedited-process-for-reinstatement-as-etp-holder">to be reinstated</a>.</td></tr>
  </tbody>
</table>

# Exchange Market Shares During Regular Trading

## Between Stocks of Different Home Exchange
When trades are grouped by their symbols' primary listing exchanges, we observe differences across their exchange market share profiles during regular hours. Notably, exchanges held higher market share for their primary listings:

<div>
<button class = "rad-button static light flat">Toggle To Table</button>

<div id="tablediv1"></div>
<div>
    <iframe src = ' https://rawgit.com/TeddyCho/TAQ/master/output/breakdownCharts/perExchangeForRegular.html ' scrolling='no' frameBorder='0' width="800" height="400"> </iframe>
</div>
</div>

<!---
To further support that primary exchange helps determine exchange market share profile, we expand each group by their constituent symbols.

## NASDAQ Stocks
Within NASDAQ stocks, exchange shares were consistent:

<div>
<button class = "rad-button static light flat">Toggle To Table</button>

<div id="tablediv2"></div>
<div>
    <iframe src = ' https://rawgit.com/TeddyCho/TAQ/master/output/breakdownCharts/NASDAQSymbolsForRegular.html ' scrolling='no' frameBorder='0' width="800" height="400"> </iframe>
</div>
</div>

## Arca Stocks
Consistency was found between our two Arca symbols, save for BATS Y, Direct Edge X, and Chicago:

<div>
<button class = "rad-button static light flat">Toggle To Table</button>

<div id="tablediv3"></div>
<div>
    <iframe src = ' https://rawgit.com/TeddyCho/TAQ/master/output/breakdownCharts/ArcaSymbolsForRegular.html ' scrolling='no' frameBorder='0' width="800" height="400"> </iframe>
</div>
</div>


## NYSEMKT Stocks 
Our NYSEMKT symbols appeared to represent two clusters of exchange market share profiles: one for CCF and ONVO, and one for LIQT and ONP:

<div>
<button class = "rad-button static light flat">Toggle To Table</button>

<div id="tablediv4"></div>
<div>
  <iframe src = ' https://rawgit.com/TeddyCho/TAQ/master/output/breakdownCharts/NYSEMKTSymbolsForRegular.html ' scrolling='no' frameBorder='0' width="800" height="400"> </iframe>
</div>
</div>
--->

# Exchange Market Shares During Open and Close Auction

In both the Open and Close epochs, exchange market shares were clearly different based on home exchange. The following graph aggregates stocks by listing exchange and shows volume share for both Open and Close combined:

<div>
<button class = "rad-button static light flat">Toggle To Table</button>

<div id="tablediv5"></div>
<div>
<iframe src = ' https://rawgit.com/TeddyCho/TAQ/master/output/breakdownCharts/perExchangeForOpenClose.html ' scrolling='no' frameBorder='0' width="800" height="400"> </iframe>
</div>
</div>

To explain why different symbols' open/close volumes adhere strongly to their home exchange, we can refer to the following documents:

* <a href = "https://www.nyse.com/publicdocs/nyse/markets/nyse-arca/NYSE_Arca_Auctions_Brochure.pdf">NYSE Arca Auctions Brochure</a>:

> The [NYSE Arca] Market Order Auction is run for NYSE Arca primary listed stocks.

> The [NYSE Arca] Closing Auction is run for NYSE Arca primary listed stocks.

* <a href="http://www1.nyse.com/pdfs/NYSEAmexEquitiesOpeningCollateral.pdf">NYSE AMEX (now NYSEMKT) Opening Auction factsheet</a>:

> DMMs...open each security [on NYSE Opening Auctions]

* <a href="https://www.nyse.com/publicdocs/nyse/markets/nyse/NYSE_Opening_and_Closing_Auctions_Fact_Sheet.pdf">NYSE Open and Closing Auctions Fact Sheet</a>:

> Only NYSE and NYSE MKT-listed names can participate in the opening auction.

Literature also suggests that exchanges' DMMs and LMMs oversee the opening/closing auctions and only deal with their respective exchanges' primary listings:

* <a href="https://www.nyse.com/publicdocs/nyse/markets/liquidity-programs/arca_mm_orientation.pdf">Arca Market Maker Orientation</a>

# Time Intervals With Concentrated Exchange Volumes

## Minute Intervals

No evidence was found that volumes concentrated in one exchange at a time.

## Second Intervals

Even in one-second intervals, volumes did not appear to concentrate in one exchange at a time.

Data tables are available for <a href = "https://github.com/TeddyCho/TAQ/tree/master/data/profileSeries/highPrice">High Price Stocks</a> and <a href = "https://github.com/TeddyCho/TAQ/tree/master/data/profileSeries/lowPrice">Low Price Stocks</a>.

### Exchange Share Over Different Trade Burst Sizes

Let us consider an investor's preference for exchanges to be consistent over time (based on bid/offer prices/volumes, fee structure). Perhaps the only reason all their volume may not be sent to their most preferred exchange is because their desired size is too big, which forces some of their size to their second preferred exchange, and then their third choice, and so on.

To begin exploring this, a "trade burst" is considered to be all trades happening in a one-second interval. For a given exchange, each trade burst is plotted as a point to designate the total size of the trade burst and the given exchange's volume share.

Trade bursts where the exchange had no representation were excluded. (Although this may be valuable.)

The above was done for GOOG and BAC:

#### GOOG

<div id="slides">
      <a href="#" class="slidesjs-previous slidesjs-navigation">Previous</a>
      <a href="#" class="slidesjs-next slidesjs-navigation">Next</a>
    <img src="https://raw.githubusercontent.com/TeddyCho/TAQ/master/output/propVsVolume/goog/NYSE.Arca.SMGOOGPropVolumePlot.jpg">
    <img src="https://raw.githubusercontent.com/TeddyCho/TAQ/master/output/propVsVolume/goog/Direct.Edge.XGOOGPropVolumePlot.jpg">
    <img src="https://raw.githubusercontent.com/TeddyCho/TAQ/master/output/propVsVolume/goog/BATSGOOGPropVolumePlot.jpg">
    <img src="https://raw.githubusercontent.com/TeddyCho/TAQ/master/output/propVsVolume/goog/NASDAQ.OMX.BXGOOGPropVolumePlot.jpg">
    <img src="https://raw.githubusercontent.com/TeddyCho/TAQ/master/output/propVsVolume/goog/BATS.YGOOGPropVolumePlot.jpg">
    <img src="https://raw.githubusercontent.com/TeddyCho/TAQ/master/output/propVsVolume/goog/Direct.Edge.AGOOGPropVolumePlot.jpg">
    <img src="https://raw.githubusercontent.com/TeddyCho/TAQ/master/output/propVsVolume/goog/NASDAQ.OMX.PSXGOOGPropVolumePlot.jpg">
    <img src="https://raw.githubusercontent.com/TeddyCho/TAQ/master/output/propVsVolume/goog/CBOEGOOGPropVolumePlot.jpg">
    <img src="https://raw.githubusercontent.com/TeddyCho/TAQ/master/output/propVsVolume/goog/NationalGOOGPropVolumePlot.jpg">
    <img src="https://raw.githubusercontent.com/TeddyCho/TAQ/master/output/propVsVolume/goog/ChicagoGOOGPropVolumePlot.jpg">
</div>

#### BAC

<div id="slides2">
      <a href="#" class="slidesjs-previous slidesjs-navigation">Previous</a>
      <a href="#" class="slidesjs-next slidesjs-navigation">Next</a>
    <img src="https://raw.githubusercontent.com/TeddyCho/TAQ/master/output/propVsVolume/bac/Direct.Edge.XBACPropVolumePlot.jpg">
    <img src="https://raw.githubusercontent.com/TeddyCho/TAQ/master/output/propVsVolume/bac/NASDAQ.OMXBACPropVolumePlot.jpg">
    <img src="https://raw.githubusercontent.com/TeddyCho/TAQ/master/output/propVsVolume/bac/NYSEBACPropVolumePlot.jpg">
    <img src="https://raw.githubusercontent.com/TeddyCho/TAQ/master/output/propVsVolume/bac/BATSBACPropVolumePlot.jpg">
    <img src="https://raw.githubusercontent.com/TeddyCho/TAQ/master/output/propVsVolume/bac/NYSE.Arca.SMBACPropVolumePlot.jpg">
    <img src="https://raw.githubusercontent.com/TeddyCho/TAQ/master/output/propVsVolume/bac/Direct.Edge.ABACPropVolumePlot.jpg">
    <img src="https://raw.githubusercontent.com/TeddyCho/TAQ/master/output/propVsVolume/bac/NASDAQ.OMX.BXBACPropVolumePlot.jpg">
    <img src="https://raw.githubusercontent.com/TeddyCho/TAQ/master/output/propVsVolume/bac/BATS.YBACPropVolumePlot.jpg">
    <img src="https://raw.githubusercontent.com/TeddyCho/TAQ/master/output/propVsVolume/bac/NASDAQ.OMX.PSXBACPropVolumePlot.jpg">
    <img src="https://raw.githubusercontent.com/TeddyCho/TAQ/master/output/propVsVolume/bac/NationalBACPropVolumePlot.jpg">
    <img src="https://raw.githubusercontent.com/TeddyCho/TAQ/master/output/propVsVolume/bac/ChicagoBACPropVolumePlot.jpg">
    <img src="https://raw.githubusercontent.com/TeddyCho/TAQ/master/output/propVsVolume/bac/CBOEBACPropVolumePlot.jpg">
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

# Exchange Volumes and Market Shares Over 2014
The following graphs illustrate the extent of day-to-day consistency for the trends in the last rChart.

With so many exchanges, it may be helpful to amalgamate categories:
![Regular Hours Market Share](https://raw.githubusercontent.com/TeddyCho/TeddyCho.github.io/master/_posts/img/Regular2014.png)
We see similar exchange market share profiles for both the opening and closing auctions, with an overwhelming showing by NYSE:
![Opening Auction Market Share](https://raw.githubusercontent.com/TeddyCho/TeddyCho.github.io/master/_posts/img/Open2014.png)
![Closing Auction Market Share](https://raw.githubusercontent.com/TeddyCho/TeddyCho.github.io/master/_posts/img/Close2014.png)
After-Hours trading has a different profile for exchange market shares:
![After-Hours Market Share](https://raw.githubusercontent.com/TeddyCho/TeddyCho.github.io/master/_posts/img/After-Hours2014.png)


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

* Some trades had an exchange code "Q", which did not exactly correspond to anything listed in the [spec sheet](www.nyxdata.com/doc/224904). We assumed "Q" referred to the NASDAQ exchange since "T/Q" corresponded to NASDAQ and "T" corresponded to NASDAQ OMX. Since NASDAQ only has three exchanges (BX, PSX, and NASDAQ), trades labeled as NASDAQ OMX and NASDAQ were combined into the NASDAQ label.

* Trades of exchange type "FINRA" are trades which happened off-exchange. Such trades are reported for TAQ publication through FINRA's ADF, TRF, or ORF, as written [here](http://www.finra.org/industry/trade-reporting-faq#100). <strong>These trades are excluded from the analysis.</strong>

* Remaining questions on pre-open and post-close trades. There is a T code for "extended hours" trades, so why do some trades have no condition codes? A lot of intermarket sweep order condition codes. Weird thing where two trades happen at the same time/exchange, and their volumes add up to a round number, but only one has a condition code.
* BAC had F, T, blank, and a 4 for 250000 traded on CHX, GOOG had @, T, and @F. Weird.

<script>
$(function(){
  $('#tablediv1').hide();
  $('#tablediv2').hide();
  $('#tablediv3').hide();
  $('#tablediv4').hide();
  $('#tablediv5').hide();
  $('#tablediv6').hide();
  $('button').click(function() {
    if ($(this).text() == 'Toggle to Chart') {
      $(this).next().toggle();
      $(this).next().next().fadeToggle("fast");
      $(this).text('Toggle to Table');
    } else {
      $(this).next().next().toggle();
      $(this).next().fadeToggle("fast");
      $(this).text('Toggle to Chart');
    }
  });
  $("#slides").slidesjs({
      width: 300, height: 250,
        navigation: {
          active: false,
          effect: "fade"
        },
        pagination: {
          effect: "fade"
        },
        effect: {
          fade: {
            speed: 100
          }
        }
      }
    );
  $("#slides2").slidesjs({
      width: 300, height: 250,
        navigation: {
          active: false,
          effect: "fade"
        },
        pagination: {
          effect: "fade"
        },
        effect: {
          fade: {
            speed: 100
          }
        }
      }
    );
var myData1 = [
      ["BATS","0.14446911111026","0.116073690071653","0.108118912666049"," 0.0560365065805209 "],
      ["BATS Y","0.0711826015760951","0.0384401636548427","0.061150738754358"," 0.0328836396755233 "],
      ["CBOE","0.00148759944354625","0.00125921545104189","0.00164971453163631"," 0.00223600944792826 "],
      ["Chicago","0.018097387622094","0.00604409545356514","0.0101006261386684"," 0.00951469320408402 "],
      ["Direct Edge A","0.0788762014052909","0.035808343771384","0.0616367444048279"," 0.0348526850689444 "],
      ["Direct Edge X","0.144061681892251","0.145732423385975","0.135344105169506"," 0.316571739232819 "],
      ["NASDAQ","0","0.443025948637689","0"," 0 "],
      ["NASDAQ OMX","0.181439041323123","0","0.177687690928391"," 0.190874518080547 "],
      ["NASDAQ OMX BX","0.0781438856458809","0.0404254144946999","0.0667459469845516"," 0.0165290576545244 "],
      ["NASDAQ OMX PSX","0.0181632697010777","0.00693137962203041","0.00879343535453272"," 0.00163112189112846 "],
      ["National","0.00181356454113983","0.00196093643726226","0.00457641663121721"," 0.0175532635503001 "],
      ["NYSE","0","0","0.250785535694706"," 0 "],
      ["NYSE Arca SM","0.260643898242613","0.161077042268921","0.113410132741556"," 0.183775222489043 "],
      ["NYSE MKT","0.00162175749662837","0.00322134675093503","0"," 0.137541543124637 "]
    ],
    container1 = document.querySelector('#tablediv1');
var hot1 = new Handsontable(container1, {
    data: myData1,
    columnSorting: true,
    rowHeaders: true,
    colHeaders: ["Exchange","Arca","NASDAQ","NYSE"," NYSEMKT "],
    contextMenu: true,
    columns: [
      {data: 0, type: 'text'},
      {data: 1, type: 'numeric', format: '0.00%'},
      {data: 2, type: 'numeric', format: '0.00%'},
      {data: 3, type: 'numeric', format: '0.00%'},
      {data: 4, type: 'numeric', format: '0.00%'}
    ]
  });
  
  var myData2 = [
    ["BATS","0.0806521152866501","0.12800625770208","0.135469794502628","0.163387184158113","0.0750055891253632"," 0.135742135882178 "],
    ["BATS Y","0.0314451559762132","0.0406009758388476","0.0424387033774359","0.058117293548598","0.0306677992669552"," 0.0362279138177863 "],
    ["CBOE","0.000820476176806325","0.00166774652826138","0.00203923337760505","0.00111297619785575","0.000784058264141885"," 0.00154789177966429 "],
    ["Chicago","0.00612760764271581","0.0088749428021301","0.000601336239394767","0.000692959875930365","0.00695311932856728"," 0.00746064109611972 "],
    ["Direct Edge A","0.0316615186826698","0.0425621998848211","0.0407161139669472","0.0463733237760386","0.0261588322847568"," 0.0363293889720277 "],
    ["Direct Edge X","0.128766059023721","0.0968793908779195","0.0776418061710318","0.0831775507759678","0.252395543319794"," 0.118346222229369 "],
    ["NASDAQ","0.493177806351307","0.463253589342193","0.505790275671493","0.438580141631013","0.374439582888612"," 0.47396539761135 "],
    ["NASDAQ OMX BX","0.05193711790922","0.039662922315642","0.0419820738071721","0.0504459828790787","0.039891791282688"," 0.0312652447573276 "],
    ["NASDAQ OMX PSX","0.00463900859732473","0.00771989031347727","0.00450457294390121","0.00987013047735106","0.00668731868486039"," 0.00650499351138754 "],
    ["National","0.00236836755430039","0.00200118808823308","0.00201202455506011","0.00161079747896695","0.00239883770659699"," 0.0014666503995349 "],
    ["NYSE Arca SM","0.168404766799072","0.156123906689075","0.146804065387331","0.139263662633021","0.184617527847664"," 0.151143519943256 "],
    ["NYSE MKT","0","0.0126469896173193","0","0.00736799656806552","0"," 0 "]
    ],
    container2 = document.querySelector('#tablediv2');
var hot2 = new Handsontable(container2, {
    data: myData2,
    columnSorting: true,
    rowHeaders: true,
    colHeaders: ["Exchange","GOOG","GT","NDAQ","STLD","TSLA"," WFM "],
    contextMenu: true,
    columns: [
      {data: 0, type: 'text'},
      {data: 1, type: 'numeric', format: '0.00%'},
      {data: 2, type: 'numeric', format: '0.00%'},
      {data: 3, type: 'numeric', format: '0.00%'},
      {data: 4, type: 'numeric', format: '0.00%'},
      {data: 5, type: 'numeric', format: '0.00%'},
      {data: 6, type: 'numeric', format: '0.00%'}
    ]
  });
  
  var myData3 = [
    ["BATS","0.14444321585521"," 0.144717622545373 "],
    ["BATS Y","0.0729249451145133"," 0.0544616891018889 "],
    ["CBOE","0.0015353514225791"," 0.00102933352510206 "],
    ["Chicago","0.0199825622150203"," 5.75490336182118e-06 "],
    ["Direct Edge A","0.0791772488567529"," 0.0759871109501171 "],
    ["Direct Edge X","0.135128073331646"," 0.229795685277318 "],
    ["NASDAQ OMX","0.18288614800685"," 0.167551456202331 "],
    ["NASDAQ OMX BX","0.0792063196274206"," 0.0679479253066949 "],
    ["NASDAQ OMX PSX","0.0184050180570935"," 0.0158432604649004 "],
    ["National","0.00181208323542482"," 0.00182778032732785 "],
    ["NYSE Arca SM","0.262708287277478"," 0.240832381395585 "],
    ["NYSE MKT","0.00179074700001166"," 0 "]
    ],
    container3 = document.querySelector('#tablediv3');
var hot3 = new Handsontable(container3, {
    data: myData3,
    columnSorting: true,
    rowHeaders: true,
    colHeaders: ["Exchange","SLV", "TBF"],
    contextMenu: true,
    columns: [
      {data: 0, type: 'text'},
      {data: 1, type: 'numeric', format: '0.00%'},
      {data: 2, type: 'numeric', format: '0.00%'}
    ]
  });
  
  var myData4 = [
    ["BATS","0.0463490828512692","0.0416419322897192","0.0229622472456781"," 0.0580457017340001 "],
["BATS Y","0.0648317602442434","0.0139494984310874","0.0233308606823946"," 0.0344591534809727 "],
["CBOE","0.0192682368542373","0","0.000613308800981294"," 0.00235153595140711 "],
["Chicago","0","0","0"," 0.0105744371299927 "],
["Direct Edge A","0.0616508354763381","0.012502095875601","0.0110569754739295"," 0.0370716039744583 "],
["Direct Edge X","0.196744495441928","0.342593916540914","0.421875365829563"," 0.312729430316456 "],
["NASDAQ OMX","0.127782906183137","0.17458690444147","0.139433814329612"," 0.193796994334966 "],
["NASDAQ OMX BX","0.0174370558392","0.00513541284791027","0.00762952722114579"," 0.017663864623371 "],
["NASDAQ OMX PSX","0.00380636335402726","0.000683590380042636","0.00218655437519309"," 0.00168232855498956 "],
["National","0.0159884455057079","0.00755327177853263","0.0074781986994884"," 0.0186166100172551 "],
["NYSE Arca SM","0.221417080491367","0.198561691413223","0.125688616154919"," 0.183684130225264 "],
["NYSE MKT","0.224723737758544","0.2027916860015","0.237744531187095"," 0.129324209656868 "]
    ],
    container4 = document.querySelector('#tablediv4');
var hot4 = new Handsontable(container4, {
    data: myData4,
    columnSorting: true,
    rowHeaders: true,
    colHeaders: ["Exchange","CCF","LIQT","ONP"," ONVO "],
    contextMenu: true,
    columns: [
      {data: 0, type: 'text'},
      {data: 1, type: 'numeric', format: '0.00%'},
      {data: 2, type: 'numeric', format: '0.00%'},
      {data: 3, type: 'numeric', format: '0.00%'},
      {data: 4, type: 'numeric', format: '0.00%'}
    ]
  });
  
  var myData5 = [
    ["BATS","0","0","0"," 0 "],
    ["BATS Y","0","0","0"," 0 "],
    ["CBOE","0","0","0"," 0 "],
    ["Chicago","0","0","0"," 0 "],
    ["Direct Edge A","0","0","0"," 0 "],
    ["Direct Edge X","0","0","0"," 0 "],
    ["NASDAQ","0","0.997080771565829","0"," 0 "],
    ["NASDAQ OMX","0.0016175949901403","0","0.000761553444762899"," 0.00886797920446521 "],
    ["NASDAQ OMX BX","0","0","0"," 0 "],
    ["NASDAQ OMX PSX","0","0","0"," 0 "],
    ["National","0","0","0"," 0 "],
    ["NYSE","0","0","0.998140595833068"," 0 "],
    ["NYSE Arca SM","0.99838240500986","0.00291922843417105","0.00109785072216892"," 0.0108586847524712 "],
    ["NYSE MKT","0","0","0"," 0.980273336043064 "]
    ],
    container5 = document.querySelector('#tablediv5');
var hot5 = new Handsontable(container5, {
    data: myData5,
    columnSorting: true,
    rowHeaders: true,
    colHeaders: ["Exchange","Arca","NASDAQ","NYSE"," NYSEMKT "],
    contextMenu: true,
    columns: [
      {data: 0, type: 'text'},
      {data: 1, type: 'numeric', format: '0.00%'},
      {data: 2, type: 'numeric', format: '0.00%'},
      {data: 3, type: 'numeric', format: '0.00%'},
      {data: 4, type: 'numeric', format: '0.00%'}
    ]
  });
  
});
</script>

