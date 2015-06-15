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

<div>
<button class = "rad-button static light flat">Toggle To Table</button>

<div id="tablediv1"></div>
<div>
    <iframe src = ' https://rawgit.com/TeddyCho/TAQ/master/output/perExchangeForRegular.html ' scrolling='no' frameBorder='0' width="800" height="400"> </iframe>
</div>
</div>

To further support that listing exchange helps determine exchange market share profile, we expand each group by their constituent symbols.

## NASDAQ Stocks
Within NASDAQ stocks, exchange shares were consistent:

<div>
<button class = "rad-button static light flat">Toggle To Table</button>

<div id="tablediv2"></div>
<div>
    <iframe src = ' https://rawgit.com/TeddyCho/TAQ/master/output/NASDAQSymbolsForRegular.html ' scrolling='no' frameBorder='0' width="800" height="400"> </iframe>
</div>
</div>

## Arca Stocks
Consistency was found between our two Arca symbols, save for BATS Y, Direct Edge X, and Chicago:

<div>
<button class = "rad-button static light flat">Toggle To Table</button>

<div id="tablediv3"></div>
<div>
    <iframe src = ' https://rawgit.com/TeddyCho/TAQ/master/output/ArcaSymbolsForRegular.html ' scrolling='no' frameBorder='0' width="800" height="400"> </iframe>
</div>
</div>


## NYSEMKT Stocks 
Our NYSEMKT symbols appeared to represent two clusters of exchange market share profiles: one for CCF and ONVO, and one for LIQT and ONP:

<div>
<button class = "rad-button static light flat">Toggle To Table</button>

<div id="tablediv4"></div>
<div>
  <iframe src = ' https://rawgit.com/TeddyCho/TAQ/master/output/NYSEMKTSymbolsForRegular.html ' scrolling='no' frameBorder='0' width="800" height="400"> </iframe>
</div>
</div>

# Exchange Market Shares During Open and Close Auction

In both the Open and Close epochs, exchange market shares were clearly different based on home exchange. The following graph aggregates stocks by listing exchange and shows volume share for both Open and Close combined:

<div>
<button class = "rad-button static light flat">Toggle To Table</button>

<div id="tablediv5"></div>
<div>
<iframe src = ' https://rawgit.com/TeddyCho/TAQ/master/output/perExchangeForOpenClose.html ' scrolling='no' frameBorder='0' width="800" height="400"> </iframe>
</div>
</div>

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
    ["BATS","0.105072903370875","0.0968274916406619","0.140575289490133","0.400718920263152","0.102681005134877","0.139487813010969","0.111471148658657","0.093818872922384","0.152658374117995","0.12255548772599","0.0831398426051529"," 0.121833281400576 "],
["BATS Y","0.0531757891136095","0.0725803528413504","0.0302791381018429","0.0330070309497434","0.0347546578717499","0.0414985655532138","0.0652821692926322","0.0304979414480798","0.0454513431813266","0.0550126458051963","0.0431226691868963"," 0.0303598778402531 "],
["CBOE","0.00251520829910772","0.00163599922141949","0.000418015892263055","0","0.00041830941009304","0.0022988966220515","0.00155150649468907","0.00135408877423164","0.00142772709079438","0.00188880048400092","0.00211840384370207"," 0.000399393607345542 "],
["Chicago","0.0093741687446426","0.0136217672951933","0.00988379391531965","2.26075554450297e-05","0.000804519779377101","0.00119634888246683","0.00575510245654589","0.0109205497007283","0.000789462477402889","0.00895635072109437","0.00200584920234348"," 0.0126220710575816 "],
["Direct Edge A","0.0586116758258619","0.0706201717237259","0.045984134953643","0.00723441774240951","0.0461765102059584","0.0375987123467113","0.0675664330816484","0.0304752603523068","0.043669064272245","0.0547524161509215","0.0312931479269666"," 0.0331341842606623 "],
["Direct Edge X","0.1710010158856","0.156711091193449","0.0812322798397423","0.044129948228698","0.0871949273386892","0.0797969091490853","0.120300219659043","0.10055430036498","0.102420590436589","0.105569148676022","0.102587984772567"," 0.079166140657972 "],
["NASDAQ OMX","0.143402617546669","0.151615956078967","0.175335243753789","0.210928492302127","0.267384361871783","0.261037756398273","0.173670079528431","0.227886481861745","0.243458922116747","0.208487636196268","0.253469855104843"," 0.270117774575639 "],
["NASDAQ OMX BX","0.0564614862467124","0.0787385002451181","0.0280812650182506","0.00547102841769719","0.0370590921175523","0.0417274290019306","0.0760567208904439","0.0421683351385571","0.0519448229456534","0.0605424334239439","0.0433856960257497"," 0.0272670436440647 "],
["NASDAQ OMX PSX","0.00997882128073693","0.0100460516712016","0.00548286446328642","0.00183121199104741","0.00551721236300868","0.00496555355203197","0.00850215659725993","0.00561010189146536","0.00618023821636397","0.00707277814170098","0.00747448327801706"," 0.00666044186696607 "],
["National","0.00621937958601774","0.00544528336283429","0.00144177253878499","0.00938213550968734","0.00237380747123058","0.0023494007938464","0.0034979855173773","0.00160276013018999","0.00304698913880179","0.00362198776462629","0.00168610327033605"," 0.00327330589267653 "],
["NYSE","0.27147388175409","0.234798469698703","0.339286364184264","0.287274207039993","0.295031364527294","0.279169318624475","0.266120336917501","0.275611212941853","0.234399820479451","0.248998907231633","0.236928777988224"," 0.259553561518155 "],
["NYSE Arca SM","0.112713052346077","0.107358865027376","0.141999837848682","0","0.120604231908387","0.108873296064945","0.100226140905771","0.179500094473479","0.114552645526629","0.122541407678601","0.192787186795202"," 0.155612923678108 "]
    ],
    container4 = document.querySelector('#tablediv4');
var hot4 = new Handsontable(container4, {
    data: myData4,
    columnSorting: true,
    rowHeaders: true,
    colHeaders: ["Exchange","AMD","BAC","BHP","BRKA","CVS","FE","GE","LTM","LUV","T","WSM"," XOM "],
    contextMenu: true,
    columns: [
      {data: 0, type: 'text'},
      {data: 1, type: 'numeric', format: '0.00%'},
      {data: 2, type: 'numeric', format: '0.00%'},
      {data: 3, type: 'numeric', format: '0.00%'},
      {data: 4, type: 'numeric', format: '0.00%'},
      {data: 5, type: 'numeric', format: '0.00%'},
      {data: 6, type: 'numeric', format: '0.00%'},
      {data: 7, type: 'numeric', format: '0.00%'},
      {data: 8, type: 'numeric', format: '0.00%'},
      {data: 9, type: 'numeric', format: '0.00%'},
      {data: 10, type: 'numeric', format: '0.00%'},
      {data: 11, type: 'numeric', format: '0.00%'},
      {data: 12, type: 'numeric', format: '0.00%'}
    ]
  });
  
  var myData5 = [
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
    container5 = document.querySelector('#tablediv5');
var hot5 = new Handsontable(container5, {
    data: myData5,
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
  
  
});
</script>

