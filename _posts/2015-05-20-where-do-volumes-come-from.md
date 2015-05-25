---
layout: post
title: Where Do Volumes Come From?
unlisted: true
---

# Tasks
> Using NYSE Trades and Quotes (TAQ) data for a representataive sample of stocks, find the exchange market shares based on stock, time of day, and date.

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
Transforming the above data (129M rows) to per-day-per-timeOfDay exchange volumes took 991 seconds on a 2.4 GHz/4GB laptop. The raw output from the code is [here](https://github.com/TeddyCho/TeddyCho.github.io/blob/master/_posts/img/breakdown5aa0ce4b018e0067.csv).

The exchanges' volumes and market shares for each epoch of each trading day can be found [here](https://github.com/TeddyCho/TeddyCho.github.io/blob/master/_posts/img/taskTwo.csv).

# Exchange Market Shares During Regular Trading

When trades are grouped by their symbols' listing exchanges, we observe differences across their exchange market share profiles during regular hours. Notably, exchanges held higher market share for their "home" stocks:

<iframe src = ' https://cdn.rawgit.com/TeddyCho/TeddyCho.github.io/master/_posts/graphs/listedExchangeRegular.html ' scrolling='no' frameBorder='0' width="800" height="400"> </iframe>

To further support that listing exchange helps determine exchange market share profile, we expand each group by their constituent symbols.

Within NASDAQ listed stocks, exchange shares were consistent:

<iframe src = ' https://cdn.rawgit.com/TeddyCho/TeddyCho.github.io/master/_posts/graphs/nasdaqReg.html ' scrolling='no' frameBorder='0' width="800" height="400"> </iframe>
 
There was consistency in the exchange market share profiles for NYSE listed stocks, as well:
 

<iframe src = ' https://cdn.rawgit.com/TeddyCho/TeddyCho.github.io/master/_posts/graphs/nyseReg.html ' scrolling='no' frameBorder='0' width="800" height="400"> </iframe>
 
Consistency was found between our two Arca symbols, save for BATS Y, Direct Edge X, and Chicago:

<iframe src = ' https://cdn.rawgit.com/TeddyCho/TeddyCho.github.io/master/_posts/graphs/arcaReg.html ' scrolling='no' frameBorder='0' width="800" height="400"> </iframe>
 
 Our NYSEMKT symbols appeared to represent two clusters of exchange market share profiles: one for CCF and ONVO, and one for LIQT and ONP:
 

<iframe src = ' https://cdn.rawgit.com/TeddyCho/TeddyCho.github.io/master/_posts/graphs/nysemktReg.html ' scrolling='no' frameBorder='0' width="800" height="400"> </iframe>

# Exchange Market Shares During Open and Close Auction

In both the Open and Close epochs, exchange market shares were clearly different based on home exchange. The following graph aggregates stocks by listing exchange and shows volume share for both Open and Close combined:


<iframe src = ' https://cdn.rawgit.com/TeddyCho/TeddyCho.github.io/master/_posts/graphs/listedExchangeOpenClose.html ' scrolling='no' frameBorder='0' width="800" height="400"> </iframe>

# Exchange Market Shares During After-Hours

When grouped by home exchange, we observe stark differences in the exchange share profiles:

<iframe src = ' https://cdn.rawgit.com/TeddyCho/TeddyCho.github.io/master/_posts/graphs/listedExchangeAfter.html ' scrolling='no' frameBorder='0' width="800" height="400"> </iframe>

Among NASDAQ listed stocks, we do see variability in their exchange share profiles for after-hours trading:

<iframe src = ' https://cdn.rawgit.com/TeddyCho/TAQ/master/data/nasdaqAfter.html ' scrolling='no' frameBorder='0' width="800" height="400"> </iframe>
 
 We also see some variability among NYSE listed stocks:

<iframe src = ' https://cdn.rawgit.com/TeddyCho/TeddyCho.github.io/master/_posts/graphs/nyseAfter.html ' scrolling='no' frameBorder='0' width="800" height="400"> </iframe>
 
 Finally, we see some variability among NYSE MKT stocks:

<iframe src = ' https://cdn.rawgit.com/TeddyCho/TeddyCho.github.io/master/_posts/graphs/nysemktAfter.html ' scrolling='no' frameBorder='0' width="800" height="400"> </iframe>

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

<iframe srcdoc=' &lt;!doctype HTML&gt;
&lt;meta charset = &#039;utf-8&#039;&gt;
&lt;html&gt;
  &lt;head&gt;
    &lt;link rel=&#039;stylesheet&#039; href=&#039;//cdnjs.cloudflare.com/ajax/libs/nvd3/1.1.15-beta/nv.d3.min.css&#039;&gt;
    
    &lt;script src=&#039;//ajax.googleapis.com/ajax/libs/jquery/1.8.2/jquery.min.js&#039; type=&#039;text/javascript&#039;&gt;&lt;/script&gt;
    &lt;script src=&#039;//d3js.org/d3.v3.min.js&#039; type=&#039;text/javascript&#039;&gt;&lt;/script&gt;
    &lt;script src=&#039;//cdnjs.cloudflare.com/ajax/libs/nvd3/1.1.15-beta/nv.d3.min.js&#039; type=&#039;text/javascript&#039;&gt;&lt;/script&gt;
    &lt;script src=&#039;//nvd3.org/assets/lib/fisheye.js&#039; type=&#039;text/javascript&#039;&gt;&lt;/script&gt;
    
    &lt;style&gt;
    .rChart {
      display: block;
      margin-left: auto; 
      margin-right: auto;
      width: 800px;
      height: 400px;
    }  
    &lt;/style&gt;
    
  &lt;/head&gt;
  &lt;body &gt;
    
    &lt;div id = &#039;chart1b382a6b5df9&#039; class = &#039;rChart nvd3&#039;&gt;&lt;/div&gt;    
    &lt;script type=&#039;text/javascript&#039;&gt;
 $(document).ready(function(){
      drawchart1b382a6b5df9()
    });
    function drawchart1b382a6b5df9(){  
      var opts = {
 &quot;dom&quot;: &quot;chart1b382a6b5df9&quot;,
&quot;width&quot;:    800,
&quot;height&quot;:    400,
&quot;x&quot;: &quot;Common&quot;,
&quot;y&quot;: &quot;Volume&quot;,
&quot;group&quot;: &quot;Exchange&quot;,
&quot;type&quot;: &quot;multiBarChart&quot;,
&quot;id&quot;: &quot;chart1b382a6b5df9&quot; 
},
        data = [
 {
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;Volume&quot;:     2677324979,
&quot;Common&quot;: &quot;Aggregate&quot; 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;Volume&quot;:     1419907352,
&quot;Common&quot;: &quot;Aggregate&quot; 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;Volume&quot;:       38740177,
&quot;Common&quot;: &quot;Aggregate&quot; 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;Volume&quot;:      240116014,
&quot;Common&quot;: &quot;Aggregate&quot; 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;Volume&quot;:     1431592980,
&quot;Common&quot;: &quot;Aggregate&quot; 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;Volume&quot;:     3457644458,
&quot;Common&quot;: &quot;Aggregate&quot; 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;Volume&quot;:    17057752606,
&quot;Common&quot;: &quot;Aggregate&quot; 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ&quot;,
&quot;Volume&quot;:     1396056128,
&quot;Common&quot;: &quot;Aggregate&quot; 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX&quot;,
&quot;Volume&quot;:     3830994390,
&quot;Common&quot;: &quot;Aggregate&quot; 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;Volume&quot;:     1542600466,
&quot;Common&quot;: &quot;Aggregate&quot; 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;Volume&quot;:      215352909,
&quot;Common&quot;: &quot;Aggregate&quot; 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;Volume&quot;:      102979263,
&quot;Common&quot;: &quot;Aggregate&quot; 
},
{
 &quot;Exchange&quot;: &quot;NYSE&quot;,
&quot;Volume&quot;:     7553778146,
&quot;Common&quot;: &quot;Aggregate&quot; 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;Volume&quot;:     3146350415,
&quot;Common&quot;: &quot;Aggregate&quot; 
},
{
 &quot;Exchange&quot;: &quot;NYSE MKT&quot;,
&quot;Volume&quot;:       47760648,
&quot;Common&quot;: &quot;Aggregate&quot; 
} 
]
  
      if(!(opts.type===&quot;pieChart&quot; || opts.type===&quot;sparklinePlus&quot; || opts.type===&quot;bulletChart&quot;)) {
        var data = d3.nest()
          .key(function(d){
            //return opts.group === undefined ? &#039;main&#039; : d[opts.group]
            //instead of main would think a better default is opts.x
            return opts.group === undefined ? opts.y : d[opts.group];
          })
          .entries(data);
      }
      
      if (opts.disabled != undefined){
        data.map(function(d, i){
          d.disabled = opts.disabled[i]
        })
      }
      
      nv.addGraph(function() {
        var chart = nv.models[opts.type]()
          .width(opts.width)
          .height(opts.height)
          
        if (opts.type != &quot;bulletChart&quot;){
          chart
            .x(function(d) { return d[opts.x] })
            .y(function(d) { return d[opts.y] })
        }
          
         
        
          
        

        
        
        chart.yAxis
  .showMaxMin(false)
  .tickFormat(function(d) {return d/1000000000;})
  .axisLabel(&quot;Volume, in billions&quot;)
  .width(    40)
      
       d3.select(&quot;#&quot; + opts.id)
        .append(&#039;svg&#039;)
        .datum(data)
        .transition().duration(500)
        .call(chart);

       nv.utils.windowResize(chart.update);
       return chart;
      });
    };
&lt;/script&gt;
    
    &lt;script&gt;&lt;/script&gt;    
  &lt;/body&gt;
&lt;/html&gt; ' scrolling='no' frameBorder='0' seamless class='rChart  nvd3  ' id='iframe-chart1b382a6b5df9'> </iframe>
 <style>iframe.rChart{ width: 100%; height: 400px;}</style>
 
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
