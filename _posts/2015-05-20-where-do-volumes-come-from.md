---
layout: post
title: Where Do Volumes Come From?
unlisted: true
---

## Tasks
> 1. Using the TAQ data, compute the market shares for the different stock exchanges for a representative sample of stocks (it should include GOOG, BAC, and then a representative sample of other stocks, the size of the sample can depend on what's feasible computationally).
> 
> 2. Focus on calendar year 2014, and compute volumes and market shares for each exchange for each trading day, dividing the day into the opening auction, regular trading, closing auction, and after-hours trading.

## Data
Attributes of the raw TAQ data:
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
Transforming the above data (129048290 rows) to per-timeOfDay-per-day exchange volumes took 991 seconds on a 2.4 GHz/4GB laptop. The raw output from the code is [here](https://github.com/TeddyCho/TeddyCho.github.io/blob/master/_posts/img/breakdown1.csv).

The exchanges' volumes and market shares for each epoch of each trading day can be found [here](https://github.com/TeddyCho/TeddyCho.github.io/blob/master/_posts/img/taskTwo.csv) (**Task #2**).

## Overall Look at Exchange Market Shares
Over all trades, the volumes were distributed across exhanges as such (**Task #1**):

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



## Regular Trading

Within NASDAQ listed stocks, exchange shares were consistent.

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
    
    &lt;div id = &#039;chart1b3824ca2f7d&#039; class = &#039;rChart nvd3&#039;&gt;&lt;/div&gt;    
    &lt;script type=&#039;text/javascript&#039;&gt;
 $(document).ready(function(){
      drawchart1b3824ca2f7d()
    });
    function drawchart1b3824ca2f7d(){  
      var opts = {
 &quot;dom&quot;: &quot;chart1b3824ca2f7d&quot;,
&quot;width&quot;:    800,
&quot;height&quot;:    400,
&quot;x&quot;: &quot;Symbol&quot;,
&quot;y&quot;: &quot;Proportion&quot;,
&quot;group&quot;: &quot;Exchange&quot;,
&quot;type&quot;: &quot;multiBarChart&quot;,
&quot;id&quot;: &quot;chart1b3824ca2f7d&quot; 
},
        data = [
 {
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;Symbol&quot;: &quot;GOOG&quot;,
&quot;Volume&quot;:       20346549,
&quot;Proportion&quot;: 0.0538840418424 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;Symbol&quot;: &quot;GOOG&quot;,
&quot;Volume&quot;:        7932841,
&quot;Proportion&quot;: 0.02100865047793 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;Symbol&quot;: &quot;GOOG&quot;,
&quot;Volume&quot;:         206986,
&quot;Proportion&quot;: 0.0005481638328343 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;Symbol&quot;: &quot;GOOG&quot;,
&quot;Volume&quot;:        1545845,
&quot;Proportion&quot;: 0.004093882292366 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;Symbol&quot;: &quot;GOOG&quot;,
&quot;Volume&quot;:        7987424,
&quot;Proportion&quot;: 0.02115320337758 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;Symbol&quot;: &quot;GOOG&quot;,
&quot;Volume&quot;:       32484516,
&quot;Proportion&quot;: 0.08602918457445 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;Symbol&quot;: &quot;GOOG&quot;,
&quot;Volume&quot;:      125323336,
&quot;Proportion&quot;: 0.3318954915083 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ&quot;,
&quot;Symbol&quot;: &quot;GOOG&quot;,
&quot;Volume&quot;:      124416655,
&quot;Proportion&quot;: 0.3294943159113 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;Symbol&quot;: &quot;GOOG&quot;,
&quot;Volume&quot;:       13102460,
&quot;Proportion&quot;: 0.03469942263321 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;Symbol&quot;: &quot;GOOG&quot;,
&quot;Volume&quot;:        1170308,
&quot;Proportion&quot;: 0.003099342558804 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;Symbol&quot;: &quot;GOOG&quot;,
&quot;Volume&quot;:         597481,
&quot;Proportion&quot;: 0.001582317040793 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;Symbol&quot;: &quot;GOOG&quot;,
&quot;Volume&quot;:       42484389,
&quot;Proportion&quot;: 0.1125119839499 
},
{
 &quot;Exchange&quot;: &quot;NYSE MKT&quot;,
&quot;Symbol&quot;: &quot;GOOG&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;Symbol&quot;: &quot;GT&quot;,
&quot;Volume&quot;:       61302902,
&quot;Proportion&quot;: 0.08409065361981 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;Symbol&quot;: &quot;GT&quot;,
&quot;Volume&quot;:       19444031,
&quot;Proportion&quot;: 0.02667184133948 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;Symbol&quot;: &quot;GT&quot;,
&quot;Volume&quot;:         798693,
&quot;Proportion&quot;: 0.001095586248292 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;Symbol&quot;: &quot;GT&quot;,
&quot;Volume&quot;:        4250259,
&quot;Proportion&quot;: 0.005830181699448 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;Symbol&quot;: &quot;GT&quot;,
&quot;Volume&quot;:       20383272,
&quot;Proportion&quot;: 0.02796022063344 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;Symbol&quot;: &quot;GT&quot;,
&quot;Volume&quot;:       46396074,
&quot;Proportion&quot;: 0.06364260191227 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;Symbol&quot;: &quot;GT&quot;,
&quot;Volume&quot;:      250104189,
&quot;Proportion&quot;: 0.3430738845946 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ&quot;,
&quot;Symbol&quot;: &quot;GT&quot;,
&quot;Volume&quot;:      221854696,
&quot;Proportion&quot;: 0.3043233808942 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;Symbol&quot;: &quot;GT&quot;,
&quot;Volume&quot;:       18994792,
&quot;Proportion&quot;: 0.02605560948244 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;Symbol&quot;: &quot;GT&quot;,
&quot;Volume&quot;:        3697098,
&quot;Proportion&quot;: 0.005071397554988 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;Symbol&quot;: &quot;GT&quot;,
&quot;Volume&quot;:         958380,
&quot;Proportion&quot;: 0.001314632716999 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;Symbol&quot;: &quot;GT&quot;,
&quot;Volume&quot;:       74768599,
&quot;Proportion&quot;: 0.1025618715432 
},
{
 &quot;Exchange&quot;: &quot;NYSE MKT&quot;,
&quot;Symbol&quot;: &quot;GT&quot;,
&quot;Volume&quot;:        6056713,
&quot;Proportion&quot;: 0.008308137760878 
},
{
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;Symbol&quot;: &quot;NDAQ&quot;,
&quot;Volume&quot;:       24849651,
&quot;Proportion&quot;: 0.09292574385373 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;Symbol&quot;: &quot;NDAQ&quot;,
&quot;Volume&quot;:        7784665,
&quot;Proportion&quot;: 0.02911090323872 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;Symbol&quot;: &quot;NDAQ&quot;,
&quot;Volume&quot;:         374063,
&quot;Proportion&quot;: 0.00139881572273 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;Symbol&quot;: &quot;NDAQ&quot;,
&quot;Volume&quot;:         110305,
&quot;Proportion&quot;: 0.0004124876512666 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;Symbol&quot;: &quot;NDAQ&quot;,
&quot;Volume&quot;:        7468685,
&quot;Proportion&quot;: 0.02792929000227 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;Symbol&quot;: &quot;NDAQ&quot;,
&quot;Volume&quot;:       14242081,
&quot;Proportion&quot;: 0.0532585335283 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;Symbol&quot;: &quot;NDAQ&quot;,
&quot;Volume&quot;:       83980917,
&quot;Proportion&quot;: 0.3140482408281 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ&quot;,
&quot;Symbol&quot;: &quot;NDAQ&quot;,
&quot;Volume&quot;:       92778703,
&quot;Proportion&quot;: 0.3469477293689 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;Symbol&quot;: &quot;NDAQ&quot;,
&quot;Volume&quot;:        7700904,
&quot;Proportion&quot;: 0.02879767738171 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;Symbol&quot;: &quot;NDAQ&quot;,
&quot;Volume&quot;:         826288,
&quot;Proportion&quot;: 0.003089919735187 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;Symbol&quot;: &quot;NDAQ&quot;,
&quot;Volume&quot;:         369072,
&quot;Proportion&quot;: 0.00138015178304 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;Symbol&quot;: &quot;NDAQ&quot;,
&quot;Volume&quot;:       26928732,
&quot;Proportion&quot;: 0.100700506906 
},
{
 &quot;Exchange&quot;: &quot;NYSE MKT&quot;,
&quot;Symbol&quot;: &quot;NDAQ&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;Symbol&quot;: &quot;STLD&quot;,
&quot;Volume&quot;:       62620762,
&quot;Proportion&quot;: 0.1093260129302 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;Symbol&quot;: &quot;STLD&quot;,
&quot;Volume&quot;:       22274386,
&quot;Proportion&quot;: 0.03888757872108 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;Symbol&quot;: &quot;STLD&quot;,
&quot;Volume&quot;:         426566,
&quot;Proportion&quot;: 0.0007447172238434 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;Symbol&quot;: &quot;STLD&quot;,
&quot;Volume&quot;:         265588,
&quot;Proportion&quot;: 0.0004636749249732 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;Symbol&quot;: &quot;STLD&quot;,
&quot;Volume&quot;:       17773321,
&quot;Proportion&quot;: 0.03102942633402 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;Symbol&quot;: &quot;STLD&quot;,
&quot;Volume&quot;:       31879132,
&quot;Proportion&quot;: 0.05565595636215 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;Symbol&quot;: &quot;STLD&quot;,
&quot;Volume&quot;:      189523165,
&quot;Proportion&quot;: 0.3308776726059 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ&quot;,
&quot;Symbol&quot;: &quot;STLD&quot;,
&quot;Volume&quot;:      168092882,
&quot;Proportion&quot;: 0.293463765117 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;Symbol&quot;: &quot;STLD&quot;,
&quot;Volume&quot;:       19334233,
&quot;Proportion&quot;: 0.03375453347173 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;Symbol&quot;: &quot;STLD&quot;,
&quot;Volume&quot;:        3782886,
&quot;Proportion&quot;: 0.006604324676688 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;Symbol&quot;: &quot;STLD&quot;,
&quot;Volume&quot;:         617364,
&quot;Proportion&quot;: 0.001077820558087 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;Symbol&quot;: &quot;STLD&quot;,
&quot;Volume&quot;:       53375035,
&quot;Proportion&quot;: 0.09318442606243 
},
{
 &quot;Exchange&quot;: &quot;NYSE MKT&quot;,
&quot;Symbol&quot;: &quot;STLD&quot;,
&quot;Volume&quot;:        2823903,
&quot;Proportion&quot;: 0.004930091011856 
},
{
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;Symbol&quot;: &quot;TSLA&quot;,
&quot;Volume&quot;:       58245452,
&quot;Proportion&quot;: 0.04352244140816 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;Symbol&quot;: &quot;TSLA&quot;,
&quot;Volume&quot;:       23815023,
&quot;Proportion&quot;: 0.01779517383008 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;Symbol&quot;: &quot;TSLA&quot;,
&quot;Volume&quot;:         608859,
&quot;Proportion&quot;: 0.0004549544941866 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;Symbol&quot;: &quot;TSLA&quot;,
&quot;Volume&quot;:        5399432,
&quot;Proportion&quot;: 0.0040345890501 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;Symbol&quot;: &quot;TSLA&quot;,
&quot;Volume&quot;:       20313593,
&quot;Proportion&quot;: 0.01517881878797 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;Symbol&quot;: &quot;TSLA&quot;,
&quot;Volume&quot;:      195997294,
&quot;Proportion&quot;: 0.1464540226123 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;Symbol&quot;: &quot;TSLA&quot;,
&quot;Volume&quot;:      561737337,
&quot;Proportion&quot;: 0.4197440228699 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ&quot;,
&quot;Symbol&quot;: &quot;TSLA&quot;,
&quot;Volume&quot;:      290770368,
&quot;Proportion&quot;: 0.2172708060452 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;Symbol&quot;: &quot;TSLA&quot;,
&quot;Volume&quot;:       30977897,
&quot;Proportion&quot;: 0.02314745033021 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;Symbol&quot;: &quot;TSLA&quot;,
&quot;Volume&quot;:        5193025,
&quot;Proportion&quot;: 0.003880356637864 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;Symbol&quot;: &quot;TSLA&quot;,
&quot;Volume&quot;:        1862813,
&quot;Proportion&quot;: 0.001391939917418 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;Symbol&quot;: &quot;TSLA&quot;,
&quot;Volume&quot;:      143364401,
&quot;Proportion&quot;: 0.1071254240166 
},
{
 &quot;Exchange&quot;: &quot;NYSE MKT&quot;,
&quot;Symbol&quot;: &quot;TSLA&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;Symbol&quot;: &quot;WFM&quot;,
&quot;Volume&quot;:       92626895,
&quot;Proportion&quot;: 0.08218697244835 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;Symbol&quot;: &quot;WFM&quot;,
&quot;Volume&quot;:       24720984,
&quot;Proportion&quot;: 0.02193469651448 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;Symbol&quot;: &quot;WFM&quot;,
&quot;Volume&quot;:        1056241,
&quot;Proportion&quot;: 0.0009371927015994 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;Symbol&quot;: &quot;WFM&quot;,
&quot;Volume&quot;:        5090947,
&quot;Proportion&quot;: 0.00451714937465 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;Symbol&quot;: &quot;WFM&quot;,
&quot;Volume&quot;:       24790228,
&quot;Proportion&quot;: 0.0219961360642 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;Symbol&quot;: &quot;WFM&quot;,
&quot;Volume&quot;:       80756377,
&quot;Proportion&quot;: 0.07165437351136 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;Symbol&quot;: &quot;WFM&quot;,
&quot;Volume&quot;:      444652557,
&quot;Proportion&quot;: 0.3945360302885 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ&quot;,
&quot;Symbol&quot;: &quot;WFM&quot;,
&quot;Volume&quot;:      323421632,
&quot;Proportion&quot;: 0.2869689711437 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;Symbol&quot;: &quot;WFM&quot;,
&quot;Volume&quot;:       21334588,
&quot;Proportion&quot;: 0.01892997920477 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;Symbol&quot;: &quot;WFM&quot;,
&quot;Volume&quot;:        4438838,
&quot;Proportion&quot;: 0.003938539194353 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;Symbol&quot;: &quot;WFM&quot;,
&quot;Volume&quot;:        1000804,
&quot;Proportion&quot;: 0.0008880039730814 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;Symbol&quot;: &quot;WFM&quot;,
&quot;Volume&quot;:      103136398,
&quot;Proportion&quot;: 0.09151195558102 
},
{
 &quot;Exchange&quot;: &quot;NYSE MKT&quot;,
&quot;Symbol&quot;: &quot;WFM&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
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
&lt;/html&gt; ' scrolling='no' frameBorder='0' seamless class='rChart  nvd3  ' id='iframe-chart1b3824ca2f7d'> </iframe>
 <style>iframe.rChart{ width: 100%; height: 400px;}</style>
 
 
 Same goes for NYSE:
 
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
    
    &lt;div id = &#039;chart1b383156ba9&#039; class = &#039;rChart nvd3&#039;&gt;&lt;/div&gt;    
    &lt;script type=&#039;text/javascript&#039;&gt;
 $(document).ready(function(){
      drawchart1b383156ba9()
    });
    function drawchart1b383156ba9(){  
      var opts = {
 &quot;dom&quot;: &quot;chart1b383156ba9&quot;,
&quot;width&quot;:    800,
&quot;height&quot;:    400,
&quot;x&quot;: &quot;Symbol&quot;,
&quot;y&quot;: &quot;Proportion&quot;,
&quot;group&quot;: &quot;Exchange&quot;,
&quot;type&quot;: &quot;multiBarChart&quot;,
&quot;id&quot;: &quot;chart1b383156ba9&quot; 
},
        data = [
 {
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;Symbol&quot;: &quot;AMD&quot;,
&quot;Volume&quot;:      251425987,
&quot;Proportion&quot;: 0.05426161691887 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;Symbol&quot;: &quot;AMD&quot;,
&quot;Volume&quot;:      127242846,
&quot;Proportion&quot;: 0.02746097429188 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;Symbol&quot;: &quot;AMD&quot;,
&quot;Volume&quot;:        6018571,
&quot;Proportion&quot;: 0.001298900713875 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;Symbol&quot;: &quot;AMD&quot;,
&quot;Volume&quot;:       22431184,
&quot;Proportion&quot;: 0.004840996460897 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;Symbol&quot;: &quot;AMD&quot;,
&quot;Volume&quot;:      140250226,
&quot;Proportion&quot;: 0.03026816808716 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;Symbol&quot;: &quot;AMD&quot;,
&quot;Volume&quot;:      409183508,
&quot;Proportion&quot;: 0.08830813006061 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;Symbol&quot;: &quot;AMD&quot;,
&quot;Volume&quot;:     2240716388,
&quot;Proportion&quot;: 0.4835812547471 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX&quot;,
&quot;Symbol&quot;: &quot;AMD&quot;,
&quot;Volume&quot;:      343144079,
&quot;Proportion&quot;: 0.07405579981943 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;Symbol&quot;: &quot;AMD&quot;,
&quot;Volume&quot;:      135105098,
&quot;Proportion&quot;: 0.02915776988264 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;Symbol&quot;: &quot;AMD&quot;,
&quot;Volume&quot;:       23878040,
&quot;Proportion&quot;: 0.005153250364901 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;Symbol&quot;: &quot;AMD&quot;,
&quot;Volume&quot;:       14882178,
&quot;Proportion&quot;: 0.003211804202063 
},
{
 &quot;Exchange&quot;: &quot;NYSE&quot;,
&quot;Symbol&quot;: &quot;AMD&quot;,
&quot;Volume&quot;:      649602195,
&quot;Proportion&quot;: 0.1401942013844 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;Symbol&quot;: &quot;AMD&quot;,
&quot;Volume&quot;:      269707884,
&quot;Proportion&quot;: 0.05820713306619 
},
{
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;Symbol&quot;: &quot;BHP&quot;,
&quot;Volume&quot;:       31568714,
&quot;Proportion&quot;: 0.09230950307911 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;Symbol&quot;: &quot;BHP&quot;,
&quot;Volume&quot;:        6799726,
&quot;Proportion&quot;: 0.01988295526178 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;Symbol&quot;: &quot;BHP&quot;,
&quot;Volume&quot;:          93873,
&quot;Proportion&quot;: 0.0002744923338513 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;Symbol&quot;: &quot;BHP&quot;,
&quot;Volume&quot;:        2219584,
&quot;Proportion&quot;: 0.006490245249849 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;Symbol&quot;: &quot;BHP&quot;,
&quot;Volume&quot;:       10326566,
&quot;Proportion&quot;: 0.03019572403151 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;Symbol&quot;: &quot;BHP&quot;,
&quot;Volume&quot;:       18242172,
&quot;Proportion&quot;: 0.05334160372841 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;Symbol&quot;: &quot;BHP&quot;,
&quot;Volume&quot;:      117419676,
&quot;Proportion&quot;: 0.3433447413559 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX&quot;,
&quot;Symbol&quot;: &quot;BHP&quot;,
&quot;Volume&quot;:       39374688,
&quot;Proportion&quot;: 0.1151348098366 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;Symbol&quot;: &quot;BHP&quot;,
&quot;Volume&quot;:        6306154,
&quot;Proportion&quot;: 0.01843971034361 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;Symbol&quot;: &quot;BHP&quot;,
&quot;Volume&quot;:        1231276,
&quot;Proportion&quot;: 0.00360035178225 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;Symbol&quot;: &quot;BHP&quot;,
&quot;Volume&quot;:         323776,
&quot;Proportion&quot;: 0.0009467475193618 
},
{
 &quot;Exchange&quot;: &quot;NYSE&quot;,
&quot;Symbol&quot;: &quot;BHP&quot;,
&quot;Volume&quot;:       76192866,
&quot;Proportion&quot;: 0.2227941752278 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;Symbol&quot;: &quot;BHP&quot;,
&quot;Volume&quot;:       31888622,
&quot;Proportion&quot;: 0.09324494024994 
},
{
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;Symbol&quot;: &quot;CVS&quot;,
&quot;Volume&quot;:       54662475,
&quot;Proportion&quot;: 0.06902762653377 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;Symbol&quot;: &quot;CVS&quot;,
&quot;Volume&quot;:       18501724,
&quot;Proportion&quot;: 0.02336392734692 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;Symbol&quot;: &quot;CVS&quot;,
&quot;Volume&quot;:         222688,
&quot;Proportion&quot;: 0.0002812098079634 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;Symbol&quot;: &quot;CVS&quot;,
&quot;Volume&quot;:         428288,
&quot;Proportion&quot;: 0.0005408409354479 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;Symbol&quot;: &quot;CVS&quot;,
&quot;Volume&quot;:       24582174,
&quot;Proportion&quot;: 0.03104230326673 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;Symbol&quot;: &quot;CVS&quot;,
&quot;Volume&quot;:       46418425,
&quot;Proportion&quot;: 0.05861706234827 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;Symbol&quot;: &quot;CVS&quot;,
&quot;Volume&quot;:      259540365,
&quot;Proportion&quot;: 0.3277468754508 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX&quot;,
&quot;Symbol&quot;: &quot;CVS&quot;,
&quot;Volume&quot;:      142342695,
&quot;Proportion&quot;: 0.1797499727239 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;Symbol&quot;: &quot;CVS&quot;,
&quot;Volume&quot;:       19728495,
&quot;Proportion&quot;: 0.02491309046898 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;Symbol&quot;: &quot;CVS&quot;,
&quot;Volume&quot;:        2937101,
&quot;Proportion&quot;: 0.003708963249834 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;Symbol&quot;: &quot;CVS&quot;,
&quot;Volume&quot;:        1263702,
&quot;Proportion&quot;: 0.001595799489613 
},
{
 &quot;Exchange&quot;: &quot;NYSE&quot;,
&quot;Symbol&quot;: &quot;CVS&quot;,
&quot;Volume&quot;:      157060642,
&quot;Proportion&quot;: 0.1983357566435 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;Symbol&quot;: &quot;CVS&quot;,
&quot;Volume&quot;:       64203947,
&quot;Proportion&quot;: 0.08107657173427 
},
{
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;Symbol&quot;: &quot;GE&quot;,
&quot;Volume&quot;:      341416414,
&quot;Proportion&quot;: 0.06579323619157 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;Symbol&quot;: &quot;GE&quot;,
&quot;Volume&quot;:      199947739,
&quot;Proportion&quot;: 0.03853127230725 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;Symbol&quot;: &quot;GE&quot;,
&quot;Volume&quot;:        4751990,
&quot;Proportion&quot;: 0.0009157403909995 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;Symbol&quot;: &quot;GE&quot;,
&quot;Volume&quot;:       17626861,
&quot;Proportion&quot;: 0.003396814510181 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;Symbol&quot;: &quot;GE&quot;,
&quot;Volume&quot;:      206944035,
&quot;Proportion&quot;: 0.03987950553892 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;Symbol&quot;: &quot;GE&quot;,
&quot;Volume&quot;:      368458297,
&quot;Proportion&quot;: 0.07100438867964 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;Symbol&quot;: &quot;GE&quot;,
&quot;Volume&quot;:     2126409576,
&quot;Proportion&quot;: 0.4097734078883 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX&quot;,
&quot;Symbol&quot;: &quot;GE&quot;,
&quot;Volume&quot;:      531920739,
&quot;Proportion&quot;: 0.1025046991918 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;Symbol&quot;: &quot;GE&quot;,
&quot;Volume&quot;:      232948285,
&quot;Proportion&quot;: 0.04489069917836 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;Symbol&quot;: &quot;GE&quot;,
&quot;Volume&quot;:       26040602,
&quot;Proportion&quot;: 0.005018198914001 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;Symbol&quot;: &quot;GE&quot;,
&quot;Volume&quot;:       10713711,
&quot;Proportion&quot;: 0.002064604071178 
},
{
 &quot;Exchange&quot;: &quot;NYSE&quot;,
&quot;Symbol&quot;: &quot;GE&quot;,
&quot;Volume&quot;:      815079527,
&quot;Proportion&quot;: 0.1570712995504 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;Symbol&quot;: &quot;GE&quot;,
&quot;Volume&quot;:      306974944,
&quot;Proportion&quot;: 0.05915613358732 
},
{
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;Symbol&quot;: &quot;LTM&quot;,
&quot;Volume&quot;:        7544857,
&quot;Proportion&quot;: 0.06046888082178 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;Symbol&quot;: &quot;LTM&quot;,
&quot;Volume&quot;:        2452626,
&quot;Proportion&quot;: 0.01965677405078 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;Symbol&quot;: &quot;LTM&quot;,
&quot;Volume&quot;:         108895,
&quot;Proportion&quot;: 0.0008727479894037 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;Symbol&quot;: &quot;LTM&quot;,
&quot;Volume&quot;:         878224,
&quot;Proportion&quot;: 0.00703859892783 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;Symbol&quot;: &quot;LTM&quot;,
&quot;Volume&quot;:        2450802,
&quot;Proportion&quot;: 0.01964215545182 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;Symbol&quot;: &quot;LTM&quot;,
&quot;Volume&quot;:        8086516,
&quot;Proportion&quot;: 0.06481005170376 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;Symbol&quot;: &quot;LTM&quot;,
&quot;Volume&quot;:       44353164,
&quot;Proportion&quot;: 0.3554721034454 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX&quot;,
&quot;Symbol&quot;: &quot;LTM&quot;,
&quot;Volume&quot;:       18326493,
&quot;Proportion&quot;: 0.1468791948076 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;Symbol&quot;: &quot;LTM&quot;,
&quot;Volume&quot;:        3391152,
&quot;Proportion&quot;: 0.02717866834806 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;Symbol&quot;: &quot;LTM&quot;,
&quot;Volume&quot;:         451161,
&quot;Proportion&quot;: 0.003615867171563 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;Symbol&quot;: &quot;LTM&quot;,
&quot;Volume&quot;:         128893,
&quot;Proportion&quot;: 0.001033023615393 
},
{
 &quot;Exchange&quot;: &quot;NYSE&quot;,
&quot;Symbol&quot;: &quot;LTM&quot;,
&quot;Volume&quot;:       22164487,
&quot;Proportion&quot;: 0.1776391153443 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;Symbol&quot;: &quot;LTM&quot;,
&quot;Volume&quot;:       14435289,
&quot;Proportion&quot;: 0.1156928183223 
},
{
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;Symbol&quot;: &quot;LUV&quot;,
&quot;Volume&quot;:      118120076,
&quot;Proportion&quot;: 0.09908695290433 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;Symbol&quot;: &quot;LUV&quot;,
&quot;Volume&quot;:       35168173,
&quot;Proportion&quot;: 0.02950139569655 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;Symbol&quot;: &quot;LUV&quot;,
&quot;Volume&quot;:        1104710,
&quot;Proportion&quot;: 0.0009267040070558 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;Symbol&quot;: &quot;LUV&quot;,
&quot;Volume&quot;:         610850,
&quot;Proportion&quot;: 0.0005124214886351 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;Symbol&quot;: &quot;LUV&quot;,
&quot;Volume&quot;:       33789127,
&quot;Proportion&quot;: 0.02834456046005 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;Symbol&quot;: &quot;LUV&quot;,
&quot;Volume&quot;:       79248374,
&quot;Proportion&quot;: 0.06647879148234 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;Symbol&quot;: &quot;LUV&quot;,
&quot;Volume&quot;:      418330741,
&quot;Proportion&quot;: 0.3509235672342 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX&quot;,
&quot;Symbol&quot;: &quot;LUV&quot;,
&quot;Volume&quot;:      188377392,
&quot;Proportion&quot;: 0.1580234486925 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;Symbol&quot;: &quot;LUV&quot;,
&quot;Volume&quot;:       40192531,
&quot;Proportion&quot;: 0.03371616037821 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;Symbol&quot;: &quot;LUV&quot;,
&quot;Volume&quot;:        4781986,
&quot;Proportion&quot;: 0.00401144697512 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;Symbol&quot;: &quot;LUV&quot;,
&quot;Volume&quot;:        2357621,
&quot;Proportion&quot;: 0.001977728840889 
},
{
 &quot;Exchange&quot;: &quot;NYSE&quot;,
&quot;Symbol&quot;: &quot;LUV&quot;,
&quot;Volume&quot;:      181367873,
&quot;Proportion&quot;: 0.1521433993177 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;Symbol&quot;: &quot;LUV&quot;,
&quot;Volume&quot;:       88635604,
&quot;Proportion&quot;: 0.0743534225223 
},
{
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;Symbol&quot;: &quot;WSM&quot;,
&quot;Volume&quot;:       11103568,
&quot;Proportion&quot;: 0.05519633981137 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;Symbol&quot;: &quot;WSM&quot;,
&quot;Volume&quot;:        5759158,
&quot;Proportion&quot;: 0.02862903545918 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;Symbol&quot;: &quot;WSM&quot;,
&quot;Volume&quot;:         282919,
&quot;Proportion&quot;: 0.001406403172664 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;Symbol&quot;: &quot;WSM&quot;,
&quot;Volume&quot;:         267887,
&quot;Proportion&quot;: 0.00133167841932 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;Symbol&quot;: &quot;WSM&quot;,
&quot;Volume&quot;:        4179291,
&quot;Proportion&quot;: 0.02077544499269 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;Symbol&quot;: &quot;WSM&quot;,
&quot;Volume&quot;:       13700924,
&quot;Proportion&quot;: 0.06810791421584 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;Symbol&quot;: &quot;WSM&quot;,
&quot;Volume&quot;:       67612022,
&quot;Proportion&quot;: 0.3361024259631 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX&quot;,
&quot;Symbol&quot;: &quot;WSM&quot;,
&quot;Volume&quot;:       33851637,
&quot;Proportion&quot;: 0.1682780218956 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;Symbol&quot;: &quot;WSM&quot;,
&quot;Volume&quot;:        5794286,
&quot;Proportion&quot;: 0.0288036583394 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;Symbol&quot;: &quot;WSM&quot;,
&quot;Volume&quot;:         998239,
&quot;Proportion&quot;: 0.004962291315455 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;Symbol&quot;: &quot;WSM&quot;,
&quot;Volume&quot;:         225184,
&quot;Proportion&quot;: 0.001119399870752 
},
{
 &quot;Exchange&quot;: &quot;NYSE&quot;,
&quot;Symbol&quot;: &quot;WSM&quot;,
&quot;Volume&quot;:       31642528,
&quot;Proportion&quot;: 0.1572964409259 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;Symbol&quot;: &quot;WSM&quot;,
&quot;Volume&quot;:       25747290,
&quot;Proportion&quot;: 0.1279909456187 
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
          
         
        chart
  .reduceXTicks(false)
          
        chart.xAxis
  .rotateLabels(    34)

        
        
        chart.yAxis
  .showMaxMin(false)
      
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
&lt;/html&gt; ' scrolling='no' frameBorder='0' seamless class='rChart  nvd3  ' id='iframe-chart1b383156ba9'> </iframe>
 <style>iframe.rChart{ width: 100%; height: 400px;}</style>
 
Consistency was found in our two Arca symbols:

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
    
    &lt;div id = &#039;chart1b3818732e73&#039; class = &#039;rChart nvd3&#039;&gt;&lt;/div&gt;    
    &lt;script type=&#039;text/javascript&#039;&gt;
 $(document).ready(function(){
      drawchart1b3818732e73()
    });
    function drawchart1b3818732e73(){  
      var opts = {
 &quot;dom&quot;: &quot;chart1b3818732e73&quot;,
&quot;width&quot;:    800,
&quot;height&quot;:    400,
&quot;x&quot;: &quot;Symbol&quot;,
&quot;y&quot;: &quot;Proportion&quot;,
&quot;group&quot;: &quot;Exchange&quot;,
&quot;type&quot;: &quot;multiBarChart&quot;,
&quot;id&quot;: &quot;chart1b3818732e73&quot; 
},
        data = [
 {
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;Symbol&quot;: &quot;SLV&quot;,
&quot;Volume&quot;:      120435717,
&quot;Proportion&quot;: 0.09359037699052 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;Symbol&quot;: &quot;SLV&quot;,
&quot;Volume&quot;:       60804296,
&quot;Proportion&quot;: 0.04725090801164 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;Symbol&quot;: &quot;SLV&quot;,
&quot;Volume&quot;:        1280165,
&quot;Proportion&quot;: 0.0009948138969444 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;Symbol&quot;: &quot;SLV&quot;,
&quot;Volume&quot;:       16661317,
&quot;Proportion&quot;: 0.01294747918666 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;Symbol&quot;: &quot;SLV&quot;,
&quot;Volume&quot;:       66017422,
&quot;Proportion&quot;: 0.05130201876012 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;Symbol&quot;: &quot;SLV&quot;,
&quot;Volume&quot;:      112668818,
&quot;Proportion&quot;: 0.08755473388095 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;Symbol&quot;: &quot;SLV&quot;,
&quot;Volume&quot;:      453045853,
&quot;Proportion&quot;: 0.3520611097143 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX&quot;,
&quot;Symbol&quot;: &quot;SLV&quot;,
&quot;Volume&quot;:      152489158,
&quot;Proportion&quot;: 0.1184990477882 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;Symbol&quot;: &quot;SLV&quot;,
&quot;Volume&quot;:       66041661,
&quot;Proportion&quot;: 0.051320854843 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;Symbol&quot;: &quot;SLV&quot;,
&quot;Volume&quot;:       15345972,
&quot;Proportion&quot;: 0.0119253269756 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;Symbol&quot;: &quot;SLV&quot;,
&quot;Volume&quot;:        1510902,
&quot;Proportion&quot;: 0.001174119200666 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;Symbol&quot;: &quot;SLV&quot;,
&quot;Volume&quot;:      219044285,
&quot;Proportion&quot;: 0.1702189161274 
},
{
 &quot;Exchange&quot;: &quot;NYSE MKT&quot;,
&quot;Symbol&quot;: &quot;SLV&quot;,
&quot;Volume&quot;:        1493112,
&quot;Proportion&quot;: 0.00116029462397 
},
{
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;Symbol&quot;: &quot;TBF&quot;,
&quot;Volume&quot;:       12573419,
&quot;Proportion&quot;: 0.08031883335943 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;Symbol&quot;: &quot;TBF&quot;,
&quot;Volume&quot;:        4731764,
&quot;Proportion&quot;: 0.03022644550477 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;Symbol&quot;: &quot;TBF&quot;,
&quot;Volume&quot;:          89431,
&quot;Proportion&quot;: 0.0005712840386666 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;Symbol&quot;: &quot;TBF&quot;,
&quot;Volume&quot;:            500,
&quot;Proportion&quot;: 3.193993350553e-06 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;Symbol&quot;: &quot;TBF&quot;,
&quot;Volume&quot;:        6601945,
&quot;Proportion&quot;: 0.04217313686143 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;Symbol&quot;: &quot;TBF&quot;,
&quot;Volume&quot;:       19965208,
&quot;Proportion&quot;: 0.1275374831888 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;Symbol&quot;: &quot;TBF&quot;,
&quot;Volume&quot;:       69661413,
&quot;Proportion&quot;: 0.4449961798243 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX&quot;,
&quot;Symbol&quot;: &quot;TBF&quot;,
&quot;Volume&quot;:       14557278,
&quot;Proportion&quot;: 0.0929916982683 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;Symbol&quot;: &quot;TBF&quot;,
&quot;Volume&quot;:        5903481,
&quot;Proportion&quot;: 0.03771135811823 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;Symbol&quot;: &quot;TBF&quot;,
&quot;Volume&quot;:        1376501,
&quot;Proportion&quot;: 0.008793070082059 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;Symbol&quot;: &quot;TBF&quot;,
&quot;Volume&quot;:         158802,
&quot;Proportion&quot;: 0.001014425064109 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;Symbol&quot;: &quot;TBF&quot;,
&quot;Volume&quot;:       20924103,
&quot;Proportion&quot;: 0.1336628916966 
},
{
 &quot;Exchange&quot;: &quot;NYSE MKT&quot;,
&quot;Symbol&quot;: &quot;TBF&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
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
          
         
        chart
  .reduceXTicks(false)
          
        chart.xAxis
  .rotateLabels(    34)

        
        
        chart.yAxis
  .showMaxMin(false)
      
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
&lt;/html&gt; ' scrolling='no' frameBorder='0' seamless class='rChart  nvd3  ' id='iframe-chart1b3818732e73'> </iframe>
 <style>iframe.rChart{ width: 100%; height: 400px;}</style>
 
 As well as in our HYSEMKT symbols:
 
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
    
    &lt;div id = &#039;chart1b38627110c8&#039; class = &#039;rChart nvd3&#039;&gt;&lt;/div&gt;    
    &lt;script type=&#039;text/javascript&#039;&gt;
 $(document).ready(function(){
      drawchart1b38627110c8()
    });
    function drawchart1b38627110c8(){  
      var opts = {
 &quot;dom&quot;: &quot;chart1b38627110c8&quot;,
&quot;width&quot;:    800,
&quot;height&quot;:    400,
&quot;x&quot;: &quot;Symbol&quot;,
&quot;y&quot;: &quot;Proportion&quot;,
&quot;group&quot;: &quot;Exchange&quot;,
&quot;type&quot;: &quot;multiBarChart&quot;,
&quot;id&quot;: &quot;chart1b38627110c8&quot; 
},
        data = [
 {
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;Symbol&quot;: &quot;CCF&quot;,
&quot;Volume&quot;:          43130,
&quot;Proportion&quot;: 0.02487232246248 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;Symbol&quot;: &quot;CCF&quot;,
&quot;Volume&quot;:          60329,
&quot;Proportion&quot;: 0.03479068726731 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;Symbol&quot;: &quot;CCF&quot;,
&quot;Volume&quot;:          17930,
&quot;Proportion&quot;: 0.01033991981805 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;Symbol&quot;: &quot;CCF&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;Symbol&quot;: &quot;CCF&quot;,
&quot;Volume&quot;:          57369,
&quot;Proportion&quot;: 0.03308370663923 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;Symbol&quot;: &quot;CCF&quot;,
&quot;Volume&quot;:         183080,
&quot;Proportion&quot;: 0.1055790585771 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;Symbol&quot;: &quot;CCF&quot;,
&quot;Volume&quot;:         803509,
&quot;Proportion&quot;: 0.4633696950964 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX&quot;,
&quot;Symbol&quot;: &quot;CCF&quot;,
&quot;Volume&quot;:         118908,
&quot;Proportion&quot;: 0.06857217990653 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;Symbol&quot;: &quot;CCF&quot;,
&quot;Volume&quot;:          16226,
&quot;Proportion&quot;: 0.009357252591612 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;Symbol&quot;: &quot;CCF&quot;,
&quot;Volume&quot;:           3542,
&quot;Proportion&quot;: 0.002042609927246 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;Symbol&quot;: &quot;CCF&quot;,
&quot;Volume&quot;:          14878,
&quot;Proportion&quot;: 0.008579884386663 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;Symbol&quot;: &quot;CCF&quot;,
&quot;Volume&quot;:         206039,
&quot;Proportion&quot;: 0.118819115415 
},
{
 &quot;Exchange&quot;: &quot;NYSE MKT&quot;,
&quot;Symbol&quot;: &quot;CCF&quot;,
&quot;Volume&quot;:         209116,
&quot;Proportion&quot;: 0.1205935679125 
},
{
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;Symbol&quot;: &quot;LIQT&quot;,
&quot;Volume&quot;:         512856,
&quot;Proportion&quot;: 0.02108551058161 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;Symbol&quot;: &quot;LIQT&quot;,
&quot;Volume&quot;:         171800,
&quot;Proportion&quot;: 0.007063368114871 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;Symbol&quot;: &quot;LIQT&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;Symbol&quot;: &quot;LIQT&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;Symbol&quot;: &quot;LIQT&quot;,
&quot;Volume&quot;:         153974,
&quot;Proportion&quot;: 0.006330471723627 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;Symbol&quot;: &quot;LIQT&quot;,
&quot;Volume&quot;:        4219337,
&quot;Proportion&quot;: 0.1734734018143 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;Symbol&quot;: &quot;LIQT&quot;,
&quot;Volume&quot;:       12006819,
&quot;Proportion&quot;: 0.4936471623145 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX&quot;,
&quot;Symbol&quot;: &quot;LIQT&quot;,
&quot;Volume&quot;:        2150187,
&quot;Proportion&quot;: 0.08840257448667 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;Symbol&quot;: &quot;LIQT&quot;,
&quot;Volume&quot;:          63247,
&quot;Proportion&quot;: 0.002600330868226 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;Symbol&quot;: &quot;LIQT&quot;,
&quot;Volume&quot;:           8419,
&quot;Proportion&quot;: 0.0003461379287491 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;Symbol&quot;: &quot;LIQT&quot;,
&quot;Volume&quot;:          93025,
&quot;Proportion&quot;: 0.00382462059887 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;Symbol&quot;: &quot;LIQT&quot;,
&quot;Volume&quot;:        2445457,
&quot;Proportion&quot;: 0.1005422759027 
},
{
 &quot;Exchange&quot;: &quot;NYSE MKT&quot;,
&quot;Symbol&quot;: &quot;LIQT&quot;,
&quot;Volume&quot;:        2497553,
&quot;Proportion&quot;: 0.1026841456659 
},
{
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;Symbol&quot;: &quot;ONP&quot;,
&quot;Volume&quot;:          80421,
&quot;Proportion&quot;: 0.009565522299332 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;Symbol&quot;: &quot;ONP&quot;,
&quot;Volume&quot;:          81712,
&quot;Proportion&quot;: 0.00971907782946 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;Symbol&quot;: &quot;ONP&quot;,
&quot;Volume&quot;:           2148,
&quot;Proportion&quot;: 0.0002554897588809 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;Symbol&quot;: &quot;ONP&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;Symbol&quot;: &quot;ONP&quot;,
&quot;Volume&quot;:          38725,
&quot;Proportion&quot;: 0.004606071188391 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;Symbol&quot;: &quot;ONP&quot;,
&quot;Volume&quot;:        1477540,
&quot;Proportion&quot;: 0.1757431742723 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;Symbol&quot;: &quot;ONP&quot;,
&quot;Volume&quot;:        4905068,
&quot;Proportion&quot;: 0.5834239481446 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX&quot;,
&quot;Symbol&quot;: &quot;ONP&quot;,
&quot;Volume&quot;:         488341,
&quot;Proportion&quot;: 0.05808478786857 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;Symbol&quot;: &quot;ONP&quot;,
&quot;Volume&quot;:          26721,
&quot;Proportion&quot;: 0.003178278327308 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;Symbol&quot;: &quot;ONP&quot;,
&quot;Volume&quot;:           7658,
&quot;Proportion&quot;: 0.000910866188785 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;Symbol&quot;: &quot;ONP&quot;,
&quot;Volume&quot;:          26191,
&quot;Proportion&quot;: 0.003115238489223 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;Symbol&quot;: &quot;ONP&quot;,
&quot;Volume&quot;:         440201,
&quot;Proportion&quot;: 0.05235886748098 
},
{
 &quot;Exchange&quot;: &quot;NYSE MKT&quot;,
&quot;Symbol&quot;: &quot;ONP&quot;,
&quot;Volume&quot;:         832656,
&quot;Proportion&quot;: 0.09903867815213 
},
{
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;Symbol&quot;: &quot;ONVO&quot;,
&quot;Volume&quot;:        8728617,
&quot;Proportion&quot;: 0.02506326721147 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;Symbol&quot;: &quot;ONVO&quot;,
&quot;Volume&quot;:        5181792,
&quot;Proportion&quot;: 0.01487894789407 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;Symbol&quot;: &quot;ONVO&quot;,
&quot;Volume&quot;:         353612,
&quot;Proportion&quot;: 0.001015358108299 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;Symbol&quot;: &quot;ONVO&quot;,
&quot;Volume&quot;:        1590130,
&quot;Proportion&quot;: 0.004565884044514 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;Symbol&quot;: &quot;ONVO&quot;,
&quot;Volume&quot;:        5574639,
&quot;Proportion&quot;: 0.01600696500539 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;Symbol&quot;: &quot;ONVO&quot;,
&quot;Volume&quot;:       47026659,
&quot;Proportion&quot;: 0.1350318980177 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;Symbol&quot;: &quot;ONVO&quot;,
&quot;Volume&quot;:      197888427,
&quot;Proportion&quot;: 0.5682149330139 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX&quot;,
&quot;Symbol&quot;: &quot;ONVO&quot;,
&quot;Volume&quot;:       29142205,
&quot;Proportion&quot;: 0.08367864818063 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;Symbol&quot;: &quot;ONVO&quot;,
&quot;Volume&quot;:        2656202,
&quot;Proportion&quot;: 0.007626992969636 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;Symbol&quot;: &quot;ONVO&quot;,
&quot;Volume&quot;:         252980,
&quot;Proportion&quot;: 0.0007264043478088 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;Symbol&quot;: &quot;ONVO&quot;,
&quot;Volume&quot;:        2799471,
&quot;Proportion&quot;: 0.008038374203355 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;Symbol&quot;: &quot;ONVO&quot;,
&quot;Volume&quot;:       27621484,
&quot;Proportion&quot;: 0.0793120644736 
},
{
 &quot;Exchange&quot;: &quot;NYSE MKT&quot;,
&quot;Symbol&quot;: &quot;ONVO&quot;,
&quot;Volume&quot;:       19447116,
&quot;Proportion&quot;: 0.05584026252962 
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
          
         
        chart
  .reduceXTicks(false)
          
        chart.xAxis
  .rotateLabels(    34)

        
        
        chart.yAxis
  .showMaxMin(false)
      
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
&lt;/html&gt; ' scrolling='no' frameBorder='0' seamless class='rChart  nvd3  ' id='iframe-chart1b38627110c8'> </iframe>
 <style>iframe.rChart{ width: 100%; height: 400px;}</style>
 
GOOG had an exchange market share profile which differed somewhat noticeably:

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
    
    &lt;div id = &#039;chart17c0622860c5&#039; class = &#039;rChart nvd3&#039;&gt;&lt;/div&gt;    
    &lt;script type=&#039;text/javascript&#039;&gt;
 $(document).ready(function(){
      drawchart17c0622860c5()
    });
    function drawchart17c0622860c5(){  
      var opts = {
 &quot;dom&quot;: &quot;chart17c0622860c5&quot;,
&quot;width&quot;:    800,
&quot;height&quot;:    400,
&quot;x&quot;: &quot;Symbol&quot;,
&quot;y&quot;: &quot;Volume&quot;,
&quot;group&quot;: &quot;Exchange&quot;,
&quot;type&quot;: &quot;multiBarChart&quot;,
&quot;id&quot;: &quot;chart17c0622860c5&quot; 
},
        data = [
 {
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;Symbol&quot;: &quot;GOOG&quot;,
&quot;Volume&quot;:       20409524 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;Symbol&quot;: &quot;GOOG&quot;,
&quot;Volume&quot;:        7946141 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;Symbol&quot;: &quot;GOOG&quot;,
&quot;Volume&quot;:         209124 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;Symbol&quot;: &quot;GOOG&quot;,
&quot;Volume&quot;:        1545845 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;Symbol&quot;: &quot;GOOG&quot;,
&quot;Volume&quot;:        8057804 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;Symbol&quot;: &quot;GOOG&quot;,
&quot;Volume&quot;:       33457970 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;Symbol&quot;: &quot;GOOG&quot;,
&quot;Volume&quot;:      127581450 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ&quot;,
&quot;Symbol&quot;: &quot;GOOG&quot;,
&quot;Volume&quot;:      148971605 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;Symbol&quot;: &quot;GOOG&quot;,
&quot;Volume&quot;:       13119403 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;Symbol&quot;: &quot;GOOG&quot;,
&quot;Volume&quot;:        1170308 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;Symbol&quot;: &quot;GOOG&quot;,
&quot;Volume&quot;:         597681 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;Symbol&quot;: &quot;GOOG&quot;,
&quot;Volume&quot;:       43342030 
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
  .tickFormat(function(d) {return d/1000000;})
  .axisLabel(&quot;Volume, in millions&quot;)
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
&lt;/html&gt; ' scrolling='no' frameBorder='0' seamless class='rChart  nvd3  ' id='iframe-chart17c0622860c5'> </iframe>
 <style>iframe.rChart{ width: 100%; height: 400px;}</style>

([SLV also had a slight difference, with no NYSE representation.](http://rcharts.github.io/viewer/?d28814252e7c73d50287))

BRKA had the most unique exchange market share profile, with higher market share for BATS and no Arca:

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
    
    &lt;div id = &#039;chart17c049c03ce&#039; class = &#039;rChart nvd3&#039;&gt;&lt;/div&gt;    
    &lt;script type=&#039;text/javascript&#039;&gt;
 $(document).ready(function(){
      drawchart17c049c03ce()
    });
    function drawchart17c049c03ce(){  
      var opts = {
 &quot;dom&quot;: &quot;chart17c049c03ce&quot;,
&quot;width&quot;:    800,
&quot;height&quot;:    400,
&quot;x&quot;: &quot;Symbol&quot;,
&quot;y&quot;: &quot;Volume&quot;,
&quot;group&quot;: &quot;Exchange&quot;,
&quot;type&quot;: &quot;multiBarChart&quot;,
&quot;id&quot;: &quot;chart17c049c03ce&quot; 
},
        data = [
 {
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;Symbol&quot;: &quot;BRKA&quot;,
&quot;Volume&quot;:          17725 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;Symbol&quot;: &quot;BRKA&quot;,
&quot;Volume&quot;:           1460 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;Symbol&quot;: &quot;BRKA&quot;,
&quot;Volume&quot;:              1 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;Symbol&quot;: &quot;BRKA&quot;,
&quot;Volume&quot;:            320 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;Symbol&quot;: &quot;BRKA&quot;,
&quot;Volume&quot;:           1952 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;Symbol&quot;: &quot;BRKA&quot;,
&quot;Volume&quot;:          16246 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX&quot;,
&quot;Symbol&quot;: &quot;BRKA&quot;,
&quot;Volume&quot;:           9330 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;Symbol&quot;: &quot;BRKA&quot;,
&quot;Volume&quot;:            242 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;Symbol&quot;: &quot;BRKA&quot;,
&quot;Volume&quot;:             81 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;Symbol&quot;: &quot;BRKA&quot;,
&quot;Volume&quot;:            415 
},
{
 &quot;Exchange&quot;: &quot;NYSE&quot;,
&quot;Symbol&quot;: &quot;BRKA&quot;,
&quot;Volume&quot;:          15606 
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
  .tickFormat(function(d) {return d/1000;})
  .axisLabel(&quot;Volume, in thousands&quot;)
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
&lt;/html&gt; ' scrolling='no' frameBorder='0' seamless class='rChart  nvd3  ' id='iframe-chart17c049c03ce'> </iframe>
 <style>iframe.rChart{ width: 100%; height: 400px;}</style>

We can also look at the way volumes were spread out over exchanges based on Time of Day. We observe different dominant exchanges between Regular, After-Hours, and the two auctions. Recommended to view in Stacked mode:

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
    
    &lt;div id = &#039;chart1504501f6739&#039; class = &#039;rChart nvd3&#039;&gt;&lt;/div&gt;    
    &lt;script type=&#039;text/javascript&#039;&gt;
 $(document).ready(function(){
      drawchart1504501f6739()
    });
    function drawchart1504501f6739(){  
      var opts = {
 &quot;dom&quot;: &quot;chart1504501f6739&quot;,
&quot;width&quot;:    800,
&quot;height&quot;:    400,
&quot;x&quot;: &quot;TOD&quot;,
&quot;y&quot;: &quot;Proportion&quot;,
&quot;group&quot;: &quot;Exchange&quot;,
&quot;type&quot;: &quot;multiBarChart&quot;,
&quot;id&quot;: &quot;chart1504501f6739&quot; 
},
        data = [
 {
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;TOD&quot;: &quot;After-Hours&quot;,
&quot;Volume&quot;:       16954567,
&quot;Proportion&quot;: 0.09181282083254 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;TOD&quot;: &quot;After-Hours&quot;,
&quot;Volume&quot;:         535422,
&quot;Proportion&quot;: 0.002899431413129 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;TOD&quot;: &quot;After-Hours&quot;,
&quot;Volume&quot;:           6938,
&quot;Proportion&quot;: 3.757084158718e-05 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;TOD&quot;: &quot;After-Hours&quot;,
&quot;Volume&quot;:           5400,
&quot;Proportion&quot;: 2.924222320132e-05 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;TOD&quot;: &quot;After-Hours&quot;,
&quot;Volume&quot;:        1723330,
&quot;Proportion&quot;: 0.00933222231658 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;TOD&quot;: &quot;After-Hours&quot;,
&quot;Volume&quot;:       83903196,
&quot;Proportion&quot;: 0.4543548119882 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;TOD&quot;: &quot;After-Hours&quot;,
&quot;Volume&quot;:        2392522,
&quot;Proportion&quot;: 0.01295604858112 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ&quot;,
&quot;TOD&quot;: &quot;After-Hours&quot;,
&quot;Volume&quot;:         528042,
&quot;Proportion&quot;: 0.002859467041421 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX&quot;,
&quot;TOD&quot;: &quot;After-Hours&quot;,
&quot;Volume&quot;:       17295220,
&quot;Proportion&quot;: 0.09365753399184 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;TOD&quot;: &quot;After-Hours&quot;,
&quot;Volume&quot;:         359606,
&quot;Proportion&quot;: 0.001947347947506 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;TOD&quot;: &quot;After-Hours&quot;,
&quot;Volume&quot;:         538520,
&quot;Proportion&quot;: 0.002916207784884 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;TOD&quot;: &quot;After-Hours&quot;,
&quot;Volume&quot;:           2000,
&quot;Proportion&quot;: 1.083045303753e-05 
},
{
 &quot;Exchange&quot;: &quot;NYSE&quot;,
&quot;TOD&quot;: &quot;After-Hours&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;TOD&quot;: &quot;After-Hours&quot;,
&quot;Volume&quot;:       60419719,
&quot;Proportion&quot;: 0.327186464585 
},
{
 &quot;Exchange&quot;: &quot;NYSE MKT&quot;,
&quot;TOD&quot;: &quot;After-Hours&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;TOD&quot;: &quot;Close&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;TOD&quot;: &quot;Close&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;TOD&quot;: &quot;Close&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;TOD&quot;: &quot;Close&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;TOD&quot;: &quot;Close&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;TOD&quot;: &quot;Close&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;TOD&quot;: &quot;Close&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ&quot;,
&quot;TOD&quot;: &quot;Close&quot;,
&quot;Volume&quot;:       16582146,
&quot;Proportion&quot;: 0.01361031266981 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX&quot;,
&quot;TOD&quot;: &quot;Close&quot;,
&quot;Volume&quot;:         703373,
&quot;Proportion&quot;: 0.0005773152916096 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;TOD&quot;: &quot;Close&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;TOD&quot;: &quot;Close&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;TOD&quot;: &quot;Close&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NYSE&quot;,
&quot;TOD&quot;: &quot;Close&quot;,
&quot;Volume&quot;:     1179426151,
&quot;Proportion&quot;: 0.9680507387923 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;TOD&quot;: &quot;Close&quot;,
&quot;Volume&quot;:       21639914,
&quot;Proportion&quot;: 0.01776163324625 
},
{
 &quot;Exchange&quot;: &quot;NYSE MKT&quot;,
&quot;TOD&quot;: &quot;Close&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;TOD&quot;: &quot;Open&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;TOD&quot;: &quot;Open&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;TOD&quot;: &quot;Open&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;TOD&quot;: &quot;Open&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;TOD&quot;: &quot;Open&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;TOD&quot;: &quot;Open&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;TOD&quot;: &quot;Open&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ&quot;,
&quot;TOD&quot;: &quot;Open&quot;,
&quot;Volume&quot;:        7444762,
&quot;Proportion&quot;: 0.01857494304589 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX&quot;,
&quot;TOD&quot;: &quot;Open&quot;,
&quot;Volume&quot;:         527004,
&quot;Proportion&quot;: 0.001314893516402 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;TOD&quot;: &quot;Open&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;TOD&quot;: &quot;Open&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;TOD&quot;: &quot;Open&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NYSE&quot;,
&quot;TOD&quot;: &quot;Open&quot;,
&quot;Volume&quot;:      377198077,
&quot;Proportion&quot;: 0.9411224693678 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;TOD&quot;: &quot;Open&quot;,
&quot;Volume&quot;:       15626110,
&quot;Proportion&quot;: 0.03898769406986 
},
{
 &quot;Exchange&quot;: &quot;NYSE MKT&quot;,
&quot;TOD&quot;: &quot;Open&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;TOD&quot;: &quot;Regular&quot;,
&quot;Volume&quot;:     1552889698,
&quot;Proportion&quot;: 0.06341785380981 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;TOD&quot;: &quot;Regular&quot;,
&quot;Volume&quot;:      921911077,
&quot;Proportion&quot;: 0.03764956518298 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;TOD&quot;: &quot;Regular&quot;,
&quot;Volume&quot;:       22510491,
&quot;Proportion&quot;: 0.0009192971202421 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;TOD&quot;: &quot;Regular&quot;,
&quot;Volume&quot;:      181152959,
&quot;Proportion&quot;:   0.0073980347 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;TOD&quot;: &quot;Regular&quot;,
&quot;Volume&quot;:      913928355,
&quot;Proportion&quot;: 0.0373235619276 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;TOD&quot;: &quot;Regular&quot;,
&quot;Volume&quot;:     1969504060,
&quot;Proportion&quot;: 0.08043180447122 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;TOD&quot;: &quot;Regular&quot;,
&quot;Volume&quot;:    10061846212,
&quot;Proportion&quot;: 0.4109117942834 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ&quot;,
&quot;TOD&quot;: &quot;Regular&quot;,
&quot;Volume&quot;:      124416655,
&quot;Proportion&quot;: 0.005081003015512 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX&quot;,
&quot;TOD&quot;: &quot;Regular&quot;,
&quot;Volume&quot;:     2504161336,
&quot;Proportion&quot;: 0.1022664634373 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;TOD&quot;: &quot;Regular&quot;,
&quot;Volume&quot;:      997894294,
&quot;Proportion&quot;: 0.04075261400474 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;TOD&quot;: &quot;Regular&quot;,
&quot;Volume&quot;:      136063325,
&quot;Proportion&quot;: 0.005556636807392 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;TOD&quot;: &quot;Regular&quot;,
&quot;Volume&quot;:       65504674,
&quot;Proportion&quot;: 0.002675119710654 
},
{
 &quot;Exchange&quot;: &quot;NYSE&quot;,
&quot;TOD&quot;: &quot;Regular&quot;,
&quot;Volume&quot;:     3237663559,
&quot;Proportion&quot;: 0.1322216732679 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;TOD&quot;: &quot;Regular&quot;,
&quot;Volume&quot;:     1795692974,
&quot;Proportion&quot;: 0.07333360164544 
},
{
 &quot;Exchange&quot;: &quot;NYSE MKT&quot;,
&quot;TOD&quot;: &quot;Regular&quot;,
&quot;Volume&quot;:        1493112,
&quot;Proportion&quot;: 6.097661582766e-05 
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
&lt;/html&gt; ' scrolling='no' frameBorder='0' seamless class='rChart  nvd3  ' id='iframe-chart1504501f6739'> </iframe>
 <style>iframe.rChart{ width: 100%; height: 400px;}</style>



## Exchange Volumes and Market Shares Over 2014
The following graphs illustrate the extent of day-to-day consistency for the trends in the last rChart.

With so many exchanges, it may be helpful to amalgamate categories:
![Regular Hours Market Share](https://raw.githubusercontent.com/TeddyCho/TeddyCho.github.io/master/_posts/img/Regular2014.png)
We see similar exchange market share profiles for both the opening and closing auctions, with an overwhelming showing by NYSE:
![Opening Auction Market Share](https://raw.githubusercontent.com/TeddyCho/TeddyCho.github.io/master/_posts/img/Open2014.png)
![Closing Auction Market Share](https://raw.githubusercontent.com/TeddyCho/TeddyCho.github.io/master/_posts/img/Close2014.png)
After-Hours trading has a different profile for exchange market shares:
![After-Hours Market Share](https://raw.githubusercontent.com/TeddyCho/TeddyCho.github.io/master/_posts/img/After-Hours2014.png)

## Notes
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

* The laptop was faster than anticipated, and I am happy to run the code on different datasets.

* In next run, make sure to include stocks with different listings (NYSE, NASDAQ, AMEX).
