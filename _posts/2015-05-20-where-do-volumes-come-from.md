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

# Regular Trading

When trades are grouped by their symbols' listing exchanges, we observe differences across their exchange market share profiles during regular hours. Notably, exchanges held higher market share for their "home" stocks:

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
    
    &lt;div id = &#039;chart1b3823a857f0&#039; class = &#039;rChart nvd3&#039;&gt;&lt;/div&gt;    
    &lt;script type=&#039;text/javascript&#039;&gt;
 $(document).ready(function(){
      drawchart1b3823a857f0()
    });
    function drawchart1b3823a857f0(){  
      var opts = {
 &quot;dom&quot;: &quot;chart1b3823a857f0&quot;,
&quot;width&quot;:    800,
&quot;height&quot;:    400,
&quot;x&quot;: &quot;ListedExchange&quot;,
&quot;y&quot;: &quot;Proportion&quot;,
&quot;group&quot;: &quot;Exchange&quot;,
&quot;type&quot;: &quot;multiBarChart&quot;,
&quot;id&quot;: &quot;chart1b3823a857f0&quot; 
},
        data = [
 {
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;ListedExchange&quot;: &quot;Arca&quot;,
&quot;Volume&quot;:      133009136,
&quot;Proportion&quot;: 0.09215099523552 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;ListedExchange&quot;: &quot;Arca&quot;,
&quot;Volume&quot;:       65536060,
&quot;Proportion&quot;: 0.04540449877679 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;ListedExchange&quot;: &quot;Arca&quot;,
&quot;Volume&quot;:        1369596,
&quot;Proportion&quot;: 0.0009488794399099 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;ListedExchange&quot;: &quot;Arca&quot;,
&quot;Volume&quot;:       16661817,
&quot;Proportion&quot;: 0.01154359065216 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;ListedExchange&quot;: &quot;Arca&quot;,
&quot;Volume&quot;:       72619367,
&quot;Proportion&quot;: 0.05031193453075 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;ListedExchange&quot;: &quot;Arca&quot;,
&quot;Volume&quot;:      132634026,
&quot;Proportion&quot;: 0.09189111263751 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;ListedExchange&quot;: &quot;Arca&quot;,
&quot;Volume&quot;:      522707266,
&quot;Proportion&quot;: 0.3621404982191 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ&quot;,
&quot;ListedExchange&quot;: &quot;Arca&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX&quot;,
&quot;ListedExchange&quot;: &quot;Arca&quot;,
&quot;Volume&quot;:      167046436,
&quot;Proportion&quot;: 0.115732616502 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;ListedExchange&quot;: &quot;Arca&quot;,
&quot;Volume&quot;:       71945142,
&quot;Proportion&quot;: 0.0498448199653 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;ListedExchange&quot;: &quot;Arca&quot;,
&quot;Volume&quot;:       16722473,
&quot;Proportion&quot;: 0.01158561416224 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;ListedExchange&quot;: &quot;Arca&quot;,
&quot;Volume&quot;:        1669704,
&quot;Proportion&quot;: 0.001156799374659 
},
{
 &quot;Exchange&quot;: &quot;NYSE&quot;,
&quot;ListedExchange&quot;: &quot;Arca&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;ListedExchange&quot;: &quot;Arca&quot;,
&quot;Volume&quot;:      239968388,
&quot;Proportion&quot;: 0.1662541870753 
},
{
 &quot;Exchange&quot;: &quot;NYSE MKT&quot;,
&quot;ListedExchange&quot;: &quot;Arca&quot;,
&quot;Volume&quot;:        1493112,
&quot;Proportion&quot;: 0.001034453428809 
},
{
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;ListedExchange&quot;: &quot;NASDAQ&quot;,
&quot;Volume&quot;:      319992211,
&quot;Proportion&quot;: 0.07252566528188 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;ListedExchange&quot;: &quot;NASDAQ&quot;,
&quot;Volume&quot;:      105971930,
&quot;Proportion&quot;: 0.02401834938556 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;ListedExchange&quot;: &quot;NASDAQ&quot;,
&quot;Volume&quot;:        3471408,
&quot;Proportion&quot;: 0.0007867884467502 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;ListedExchange&quot;: &quot;NASDAQ&quot;,
&quot;Volume&quot;:       16662376,
&quot;Proportion&quot;: 0.003776497874121 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;ListedExchange&quot;: &quot;NASDAQ&quot;,
&quot;Volume&quot;:       98716523,
&quot;Proportion&quot;: 0.02237392429808 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;ListedExchange&quot;: &quot;NASDAQ&quot;,
&quot;Volume&quot;:      401755474,
&quot;Proportion&quot;: 0.09105716336479 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;ListedExchange&quot;: &quot;NASDAQ&quot;,
&quot;Volume&quot;:     1655321501,
&quot;Proportion&quot;: 0.3751756729961 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ&quot;,
&quot;ListedExchange&quot;: &quot;NASDAQ&quot;,
&quot;Volume&quot;:     1221334936,
&quot;Proportion&quot;: 0.2768133902028 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX&quot;,
&quot;ListedExchange&quot;: &quot;NASDAQ&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;ListedExchange&quot;: &quot;NASDAQ&quot;,
&quot;Volume&quot;:      111444874,
&quot;Proportion&quot;: 0.02525878240551 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;ListedExchange&quot;: &quot;NASDAQ&quot;,
&quot;Volume&quot;:       19108443,
&quot;Proportion&quot;: 0.004330894607544 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;ListedExchange&quot;: &quot;NASDAQ&quot;,
&quot;Volume&quot;:        5405914,
&quot;Proportion&quot;: 0.00122524078971 
},
{
 &quot;Exchange&quot;: &quot;NYSE&quot;,
&quot;ListedExchange&quot;: &quot;NASDAQ&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;ListedExchange&quot;: &quot;NASDAQ&quot;,
&quot;Volume&quot;:      444057554,
&quot;Proportion&quot;: 0.1006448545315 
},
{
 &quot;Exchange&quot;: &quot;NYSE MKT&quot;,
&quot;ListedExchange&quot;: &quot;NASDAQ&quot;,
&quot;Volume&quot;:        8880616,
&quot;Proportion&quot;: 0.002012775815699 
},
{
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;ListedExchange&quot;: &quot;NYSE&quot;,
&quot;Volume&quot;:     2196380809,
&quot;Proportion&quot;: 0.06283464780224 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;ListedExchange&quot;: &quot;NYSE&quot;,
&quot;Volume&quot;:     1242246206,
&quot;Proportion&quot;: 0.03553851067986 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;ListedExchange&quot;: &quot;NYSE&quot;,
&quot;Volume&quot;:       33513113,
&quot;Proportion&quot;: 0.000958752072265 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;ListedExchange&quot;: &quot;NYSE&quot;,
&quot;Volume&quot;:      205189091,
&quot;Proportion&quot;: 0.005870104224648 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;ListedExchange&quot;: &quot;NYSE&quot;,
&quot;Volume&quot;:     1252119164,
&quot;Proportion&quot;: 0.03582095889474 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;ListedExchange&quot;: &quot;NYSE&quot;,
&quot;Volume&quot;:     2749446770,
&quot;Proportion&quot;: 0.07865690627784 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;ListedExchange&quot;: &quot;NYSE&quot;,
&quot;Volume&quot;:    14640439279,
&quot;Proportion&quot;: 0.4188375904563 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ&quot;,
&quot;ListedExchange&quot;: &quot;NYSE&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX&quot;,
&quot;ListedExchange&quot;: &quot;NYSE&quot;,
&quot;Volume&quot;:     3609635213,
&quot;Proportion&quot;: 0.1032654066062 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;ListedExchange&quot;: &quot;NYSE&quot;,
&quot;Volume&quot;:     1355910020,
&quot;Proportion&quot;: 0.03879023537682 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;ListedExchange&quot;: &quot;NYSE&quot;,
&quot;Volume&quot;:      178634174,
&quot;Proportion&quot;: 0.005110414078807 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;ListedExchange&quot;: &quot;NYSE&quot;,
&quot;Volume&quot;:       92967580,
&quot;Proportion&quot;: 0.002659641316474 
},
{
 &quot;Exchange&quot;: &quot;NYSE&quot;,
&quot;ListedExchange&quot;: &quot;NYSE&quot;,
&quot;Volume&quot;:     5094580811,
&quot;Proportion&quot;: 0.145747126203 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;ListedExchange&quot;: &quot;NYSE&quot;,
&quot;Volume&quot;:     2303869258,
&quot;Proportion&quot;: 0.06590970601075 
},
{
 &quot;Exchange&quot;: &quot;NYSE MKT&quot;,
&quot;ListedExchange&quot;: &quot;NYSE&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;ListedExchange&quot;: &quot;NYSEMKT&quot;,
&quot;Volume&quot;:        9365024,
&quot;Proportion&quot;: 0.02446917277001 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;ListedExchange&quot;: &quot;NYSEMKT&quot;,
&quot;Volume&quot;:        5495633,
&quot;Proportion&quot;: 0.01435912960368 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;ListedExchange&quot;: &quot;NYSEMKT&quot;,
&quot;Volume&quot;:         373690,
&quot;Proportion&quot;: 0.0009763867313556 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;ListedExchange&quot;: &quot;NYSEMKT&quot;,
&quot;Volume&quot;:        1590130,
&quot;Proportion&quot;: 0.004154732085767 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;ListedExchange&quot;: &quot;NYSEMKT&quot;,
&quot;Volume&quot;:        5824707,
&quot;Proportion&quot;: 0.01521894251608 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;ListedExchange&quot;: &quot;NYSEMKT&quot;,
&quot;Volume&quot;:       52906616,
&quot;Proportion&quot;: 0.138235751193 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;ListedExchange&quot;: &quot;NYSEMKT&quot;,
&quot;Volume&quot;:      215603823,
&quot;Proportion&quot;: 0.5633351494734 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ&quot;,
&quot;ListedExchange&quot;: &quot;NYSEMKT&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX&quot;,
&quot;ListedExchange&quot;: &quot;NYSEMKT&quot;,
&quot;Volume&quot;:       31899641,
&quot;Proportion&quot;: 0.08334819290697 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;ListedExchange&quot;: &quot;NYSEMKT&quot;,
&quot;Volume&quot;:        2762396,
&quot;Proportion&quot;: 0.007217658490058 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;ListedExchange&quot;: &quot;NYSEMKT&quot;,
&quot;Volume&quot;:         272599,
&quot;Proportion&quot;: 0.0007122535967802 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;ListedExchange&quot;: &quot;NYSEMKT&quot;,
&quot;Volume&quot;:        2933565,
&quot;Proportion&quot;: 0.007664893204445 
},
{
 &quot;Exchange&quot;: &quot;NYSE&quot;,
&quot;ListedExchange&quot;: &quot;NYSEMKT&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;ListedExchange&quot;: &quot;NYSEMKT&quot;,
&quot;Volume&quot;:       30713181,
&quot;Proportion&quot;: 0.08024818005866 
},
{
 &quot;Exchange&quot;: &quot;NYSE MKT&quot;,
&quot;ListedExchange&quot;: &quot;NYSEMKT&quot;,
&quot;Volume&quot;:       22986441,
&quot;Proportion&quot;: 0.06005955736971 
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
&lt;/html&gt; ' scrolling='no' frameBorder='0' seamless class='rChart  nvd3  ' id='iframe-chart1b3823a857f0'> </iframe>
 <style>iframe.rChart{ width: 100%; height: 400px;}</style>

To further support that listing exchange helps determine exchange market share profile, we expand each group by their constituent symbols.

Within NASDAQ listed stocks, exchange shares were consistent:

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
 
 
There was consistency in the exchange market share profiles for NYSE listed stocks, as well:
 
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
 
Consistency was found between our two Arca symbols, save for BATS Y, Direct Edge X, and Chicago:

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
 
 Our NYSEMKT symbols appeared to represent two clusters of exchange market share profiles: one for CCF and ONVO, and one for LIQT and ONP:
 
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

# Open and Close Auction

In both the Open and Close epochs, exchange market shares were clearly different based on home exchange. The following graph aggregates stocks by listing exchange and shows volume share for both Open and Close combined:

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
    
    &lt;div id = &#039;chart1b38233a3675&#039; class = &#039;rChart nvd3&#039;&gt;&lt;/div&gt;    
    &lt;script type=&#039;text/javascript&#039;&gt;
 $(document).ready(function(){
      drawchart1b38233a3675()
    });
    function drawchart1b38233a3675(){  
      var opts = {
 &quot;dom&quot;: &quot;chart1b38233a3675&quot;,
&quot;width&quot;:    800,
&quot;height&quot;:    400,
&quot;x&quot;: &quot;ListedExchange&quot;,
&quot;y&quot;: &quot;Proportion&quot;,
&quot;group&quot;: &quot;Exchange&quot;,
&quot;type&quot;: &quot;multiBarChart&quot;,
&quot;id&quot;: &quot;chart1b38233a3675&quot; 
},
        data = [
 {
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;ListedExchange&quot;: &quot;Arca&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;ListedExchange&quot;: &quot;Arca&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;ListedExchange&quot;: &quot;Arca&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;ListedExchange&quot;: &quot;Arca&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;ListedExchange&quot;: &quot;Arca&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;ListedExchange&quot;: &quot;Arca&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;ListedExchange&quot;: &quot;Arca&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ&quot;,
&quot;ListedExchange&quot;: &quot;Arca&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX&quot;,
&quot;ListedExchange&quot;: &quot;Arca&quot;,
&quot;Volume&quot;:          64189,
&quot;Proportion&quot;: 0.00161759499014 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;ListedExchange&quot;: &quot;Arca&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;ListedExchange&quot;: &quot;Arca&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;ListedExchange&quot;: &quot;Arca&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NYSE&quot;,
&quot;ListedExchange&quot;: &quot;Arca&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;ListedExchange&quot;: &quot;Arca&quot;,
&quot;Volume&quot;:       39617561,
&quot;Proportion&quot;: 0.9983824050099 
},
{
 &quot;Exchange&quot;: &quot;NYSE MKT&quot;,
&quot;ListedExchange&quot;: &quot;Arca&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;ListedExchange&quot;: &quot;NASDAQ&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;ListedExchange&quot;: &quot;NASDAQ&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;ListedExchange&quot;: &quot;NASDAQ&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;ListedExchange&quot;: &quot;NASDAQ&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;ListedExchange&quot;: &quot;NASDAQ&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;ListedExchange&quot;: &quot;NASDAQ&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;ListedExchange&quot;: &quot;NASDAQ&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ&quot;,
&quot;ListedExchange&quot;: &quot;NASDAQ&quot;,
&quot;Volume&quot;:      171240260,
&quot;Proportion&quot;: 0.9970807715658 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX&quot;,
&quot;ListedExchange&quot;: &quot;NASDAQ&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;ListedExchange&quot;: &quot;NASDAQ&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;ListedExchange&quot;: &quot;NASDAQ&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;ListedExchange&quot;: &quot;NASDAQ&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NYSE&quot;,
&quot;ListedExchange&quot;: &quot;NASDAQ&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;ListedExchange&quot;: &quot;NASDAQ&quot;,
&quot;Volume&quot;:         501353,
&quot;Proportion&quot;: 0.002919228434171 
},
{
 &quot;Exchange&quot;: &quot;NYSE MKT&quot;,
&quot;ListedExchange&quot;: &quot;NASDAQ&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;ListedExchange&quot;: &quot;NYSE&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;ListedExchange&quot;: &quot;NYSE&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;ListedExchange&quot;: &quot;NYSE&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;ListedExchange&quot;: &quot;NYSE&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;ListedExchange&quot;: &quot;NYSE&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;ListedExchange&quot;: &quot;NYSE&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;ListedExchange&quot;: &quot;NYSE&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ&quot;,
&quot;ListedExchange&quot;: &quot;NYSE&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX&quot;,
&quot;ListedExchange&quot;: &quot;NYSE&quot;,
&quot;Volume&quot;:        1876299,
&quot;Proportion&quot;: 0.0007615534447629 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;ListedExchange&quot;: &quot;NYSE&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;ListedExchange&quot;: &quot;NYSE&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;ListedExchange&quot;: &quot;NYSE&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NYSE&quot;,
&quot;ListedExchange&quot;: &quot;NYSE&quot;,
&quot;Volume&quot;:     2459197335,
&quot;Proportion&quot;: 0.9981405958331 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;ListedExchange&quot;: &quot;NYSE&quot;,
&quot;Volume&quot;:        2704861,
&quot;Proportion&quot;: 0.001097850722169 
},
{
 &quot;Exchange&quot;: &quot;NYSE MKT&quot;,
&quot;ListedExchange&quot;: &quot;NYSE&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;ListedExchange&quot;: &quot;NYSEMKT&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;ListedExchange&quot;: &quot;NYSEMKT&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;ListedExchange&quot;: &quot;NYSEMKT&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;ListedExchange&quot;: &quot;NYSEMKT&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;ListedExchange&quot;: &quot;NYSEMKT&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;ListedExchange&quot;: &quot;NYSEMKT&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;ListedExchange&quot;: &quot;NYSEMKT&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ&quot;,
&quot;ListedExchange&quot;: &quot;NYSEMKT&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX&quot;,
&quot;ListedExchange&quot;: &quot;NYSEMKT&quot;,
&quot;Volume&quot;:         130273,
&quot;Proportion&quot;: 0.008867979204465 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;ListedExchange&quot;: &quot;NYSEMKT&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;ListedExchange&quot;: &quot;NYSEMKT&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;ListedExchange&quot;: &quot;NYSEMKT&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NYSE&quot;,
&quot;ListedExchange&quot;: &quot;NYSEMKT&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;ListedExchange&quot;: &quot;NYSEMKT&quot;,
&quot;Volume&quot;:         159517,
&quot;Proportion&quot;: 0.01085868475247 
},
{
 &quot;Exchange&quot;: &quot;NYSE MKT&quot;,
&quot;ListedExchange&quot;: &quot;NYSEMKT&quot;,
&quot;Volume&quot;:       14400479,
&quot;Proportion&quot;: 0.9802733360431 
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
&lt;/html&gt; ' scrolling='no' frameBorder='0' seamless class='rChart  nvd3  ' id='iframe-chart1b38233a3675'> </iframe>
 <style>iframe.rChart{ width: 100%; height: 400px;}</style>

# After-Hours Exchange Shares

When grouped by home exchange, we observe stark differences in the exchange share profiles:

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
    
    &lt;div id = &#039;chart1b3810b61b8&#039; class = &#039;rChart nvd3&#039;&gt;&lt;/div&gt;    
    &lt;script type=&#039;text/javascript&#039;&gt;
 $(document).ready(function(){
      drawchart1b3810b61b8()
    });
    function drawchart1b3810b61b8(){  
      var opts = {
 &quot;dom&quot;: &quot;chart1b3810b61b8&quot;,
&quot;width&quot;:    800,
&quot;height&quot;:    400,
&quot;x&quot;: &quot;ListedExchange&quot;,
&quot;y&quot;: &quot;Proportion&quot;,
&quot;group&quot;: &quot;Exchange&quot;,
&quot;type&quot;: &quot;multiBarChart&quot;,
&quot;id&quot;: &quot;chart1b3810b61b8&quot; 
},
        data = [
 {
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;ListedExchange&quot;: &quot;Arca&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;: null 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;ListedExchange&quot;: &quot;Arca&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;: null 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;ListedExchange&quot;: &quot;Arca&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;: null 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;ListedExchange&quot;: &quot;Arca&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;: null 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;ListedExchange&quot;: &quot;Arca&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;: null 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;ListedExchange&quot;: &quot;Arca&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;: null 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;ListedExchange&quot;: &quot;Arca&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;: null 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ&quot;,
&quot;ListedExchange&quot;: &quot;Arca&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;: null 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX&quot;,
&quot;ListedExchange&quot;: &quot;Arca&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;: null 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;ListedExchange&quot;: &quot;Arca&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;: null 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;ListedExchange&quot;: &quot;Arca&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;: null 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;ListedExchange&quot;: &quot;Arca&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;: null 
},
{
 &quot;Exchange&quot;: &quot;NYSE&quot;,
&quot;ListedExchange&quot;: &quot;Arca&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;: null 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;ListedExchange&quot;: &quot;Arca&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;: null 
},
{
 &quot;Exchange&quot;: &quot;NYSE MKT&quot;,
&quot;ListedExchange&quot;: &quot;Arca&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;: null 
},
{
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;ListedExchange&quot;: &quot;NASDAQ&quot;,
&quot;Volume&quot;:         299989,
&quot;Proportion&quot;: 0.006189770805841 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;ListedExchange&quot;: &quot;NASDAQ&quot;,
&quot;Volume&quot;:          85558,
&quot;Proportion&quot;: 0.001765346098044 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;ListedExchange&quot;: &quot;NASDAQ&quot;,
&quot;Volume&quot;:           7070,
&quot;Proportion&quot;: 0.0001458776141702 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;ListedExchange&quot;: &quot;NASDAQ&quot;,
&quot;Volume&quot;:           7200,
&quot;Proportion&quot;: 0.0001485599465382 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;ListedExchange&quot;: &quot;NASDAQ&quot;,
&quot;Volume&quot;:         374392,
&quot;Proportion&quot;: 0.007724952153381 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;ListedExchange&quot;: &quot;NASDAQ&quot;,
&quot;Volume&quot;:       12129527,
&quot;Proportion&quot;: 0.2502724837019 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;ListedExchange&quot;: &quot;NASDAQ&quot;,
&quot;Volume&quot;:       23508813,
&quot;Proportion&quot;: 0.4850650003413 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ&quot;,
&quot;ListedExchange&quot;: &quot;NASDAQ&quot;,
&quot;Volume&quot;:        3480932,
&quot;Proportion&quot;: 0.07182320441989 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX&quot;,
&quot;ListedExchange&quot;: &quot;NASDAQ&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;ListedExchange&quot;: &quot;NASDAQ&quot;,
&quot;Volume&quot;:         150346,
&quot;Proportion&quot;: 0.003102138016977 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;ListedExchange&quot;: &quot;NASDAQ&quot;,
&quot;Volume&quot;:           2900,
&quot;Proportion&quot;: 5.983664513345e-05 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;ListedExchange&quot;: &quot;NASDAQ&quot;,
&quot;Volume&quot;:            700,
&quot;Proportion&quot;: 1.444332813566e-05 
},
{
 &quot;Exchange&quot;: &quot;NYSE&quot;,
&quot;ListedExchange&quot;: &quot;NASDAQ&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;ListedExchange&quot;: &quot;NASDAQ&quot;,
&quot;Volume&quot;:        8417857,
&quot;Proportion&quot;: 0.1736883869287 
},
{
 &quot;Exchange&quot;: &quot;NYSE MKT&quot;,
&quot;ListedExchange&quot;: &quot;NASDAQ&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;ListedExchange&quot;: &quot;NYSE&quot;,
&quot;Volume&quot;:       18277810,
&quot;Proportion&quot;: 0.08037021302254 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;ListedExchange&quot;: &quot;NYSE&quot;,
&quot;Volume&quot;:         571965,
&quot;Proportion&quot;: 0.002515014046619 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;ListedExchange&quot;: &quot;NYSE&quot;,
&quot;Volume&quot;:           5300,
&quot;Proportion&quot;: 2.330487782833e-05 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;ListedExchange&quot;: &quot;NYSE&quot;,
&quot;Volume&quot;:           5400,
&quot;Proportion&quot;: 2.374459250434e-05 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;ListedExchange&quot;: &quot;NYSE&quot;,
&quot;Volume&quot;:        1938175,
&quot;Proportion&quot;: 0.008522439921685 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;ListedExchange&quot;: &quot;NYSE&quot;,
&quot;Volume&quot;:      108770045,
&quot;Proportion&quot;: 0.4782778509636 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;ListedExchange&quot;: &quot;NYSE&quot;,
&quot;Volume&quot;:         171924,
&quot;Proportion&quot;: 0.0007559750595771 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ&quot;,
&quot;ListedExchange&quot;: &quot;NYSE&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX&quot;,
&quot;ListedExchange&quot;: &quot;NYSE&quot;,
&quot;Volume&quot;:       20341139,
&quot;Proportion&quot;: 0.08944297344984 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;ListedExchange&quot;: &quot;NYSE&quot;,
&quot;Volume&quot;:         387688,
&quot;Proportion&quot;: 0.001704721033115 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;ListedExchange&quot;: &quot;NYSE&quot;,
&quot;Volume&quot;:         612320,
&quot;Proportion&quot;: 0.002692460904122 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;ListedExchange&quot;: &quot;NYSE&quot;,
&quot;Volume&quot;:           1800,
&quot;Proportion&quot;: 7.914864168113e-06 
},
{
 &quot;Exchange&quot;: &quot;NYSE&quot;,
&quot;ListedExchange&quot;: &quot;NYSE&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;ListedExchange&quot;: &quot;NYSE&quot;,
&quot;Volume&quot;:       76336635,
&quot;Proportion&quot;: 0.3356633872644 
},
{
 &quot;Exchange&quot;: &quot;NYSE MKT&quot;,
&quot;ListedExchange&quot;: &quot;NYSE&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;ListedExchange&quot;: &quot;NYSEMKT&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;ListedExchange&quot;: &quot;NYSEMKT&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;ListedExchange&quot;: &quot;NYSEMKT&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;ListedExchange&quot;: &quot;NYSEMKT&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;ListedExchange&quot;: &quot;NYSEMKT&quot;,
&quot;Volume&quot;:            652,
&quot;Proportion&quot;: 0.08047395704764 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;ListedExchange&quot;: &quot;NYSEMKT&quot;,
&quot;Volume&quot;:           2000,
&quot;Proportion&quot;: 0.2468526289805 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;ListedExchange&quot;: &quot;NYSEMKT&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ&quot;,
&quot;ListedExchange&quot;: &quot;NYSEMKT&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX&quot;,
&quot;ListedExchange&quot;: &quot;NYSEMKT&quot;,
&quot;Volume&quot;:           1200,
&quot;Proportion&quot;: 0.1481115773883 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;ListedExchange&quot;: &quot;NYSEMKT&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;ListedExchange&quot;: &quot;NYSEMKT&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;ListedExchange&quot;: &quot;NYSEMKT&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NYSE&quot;,
&quot;ListedExchange&quot;: &quot;NYSEMKT&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;ListedExchange&quot;: &quot;NYSEMKT&quot;,
&quot;Volume&quot;:           4250,
&quot;Proportion&quot;: 0.5245618365836 
},
{
 &quot;Exchange&quot;: &quot;NYSE MKT&quot;,
&quot;ListedExchange&quot;: &quot;NYSEMKT&quot;,
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
&lt;/html&gt; ' scrolling='no' frameBorder='0' seamless class='rChart  nvd3  ' id='iframe-chart1b3810b61b8'> </iframe>
 <style>iframe.rChart{ width: 100%; height: 400px;}</style>

Among NASDAQ listed stocks, we do see variability in their exchange share profiles for after-hours trading:

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
    
    &lt;div id = &#039;chart1b382e4b1cd6&#039; class = &#039;rChart nvd3&#039;&gt;&lt;/div&gt;    
    &lt;script type=&#039;text/javascript&#039;&gt;
 $(document).ready(function(){
      drawchart1b382e4b1cd6()
    });
    function drawchart1b382e4b1cd6(){  
      var opts = {
 &quot;dom&quot;: &quot;chart1b382e4b1cd6&quot;,
&quot;width&quot;:    800,
&quot;height&quot;:    400,
&quot;x&quot;: &quot;Symbol&quot;,
&quot;y&quot;: &quot;Proportion&quot;,
&quot;group&quot;: &quot;Exchange&quot;,
&quot;type&quot;: &quot;multiBarChart&quot;,
&quot;id&quot;: &quot;chart1b382e4b1cd6&quot; 
},
        data = [
 {
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;Symbol&quot;: &quot;GOOG&quot;,
&quot;Volume&quot;:          62975,
&quot;Proportion&quot;: 0.01328975657851 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;Symbol&quot;: &quot;GOOG&quot;,
&quot;Volume&quot;:          13300,
&quot;Proportion&quot;: 0.002806729059058 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;Symbol&quot;: &quot;GOOG&quot;,
&quot;Volume&quot;:           2138,
&quot;Proportion&quot;: 0.00045118697205 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;Symbol&quot;: &quot;GOOG&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;Symbol&quot;: &quot;GOOG&quot;,
&quot;Volume&quot;:          70380,
&quot;Proportion&quot;: 0.0148524504644 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;Symbol&quot;: &quot;GOOG&quot;,
&quot;Volume&quot;:         973454,
&quot;Proportion&quot;: 0.2054301977035 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;Symbol&quot;: &quot;GOOG&quot;,
&quot;Volume&quot;:        2258114,
&quot;Proportion&quot;: 0.4765349009372 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ&quot;,
&quot;Symbol&quot;: &quot;GOOG&quot;,
&quot;Volume&quot;:         528042,
&quot;Proportion&quot;: 0.1114338966769 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;Symbol&quot;: &quot;GOOG&quot;,
&quot;Volume&quot;:          16943,
&quot;Proportion&quot;: 0.003575519582528 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;Symbol&quot;: &quot;GOOG&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;Symbol&quot;: &quot;GOOG&quot;,
&quot;Volume&quot;:            200,
&quot;Proportion&quot;: 4.220645201591e-05 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;Symbol&quot;: &quot;GOOG&quot;,
&quot;Volume&quot;:         813066,
&quot;Proportion&quot;: 0.1715831555738 
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
&quot;Volume&quot;:           1600,
&quot;Proportion&quot;: 0.0002978910061492 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;Symbol&quot;: &quot;GT&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;Symbol&quot;: &quot;GT&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;Symbol&quot;: &quot;GT&quot;,
&quot;Volume&quot;:           1000,
&quot;Proportion&quot;: 0.0001861818788433 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;Symbol&quot;: &quot;GT&quot;,
&quot;Volume&quot;:            200,
&quot;Proportion&quot;: 3.723637576865e-05 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;Symbol&quot;: &quot;GT&quot;,
&quot;Volume&quot;:          77417,
&quot;Proportion&quot;: 0.01441364251441 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;Symbol&quot;: &quot;GT&quot;,
&quot;Volume&quot;:        5108775,
&quot;Proportion&quot;: 0.9511613280875 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ&quot;,
&quot;Symbol&quot;: &quot;GT&quot;,
&quot;Volume&quot;:         108862,
&quot;Proportion&quot;: 0.02026813169463 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;Symbol&quot;: &quot;GT&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;Symbol&quot;: &quot;GT&quot;,
&quot;Volume&quot;:            200,
&quot;Proportion&quot;: 3.723637576865e-05 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;Symbol&quot;: &quot;GT&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;Symbol&quot;: &quot;GT&quot;,
&quot;Volume&quot;:          73038,
&quot;Proportion&quot;: 0.01359835206695 
},
{
 &quot;Exchange&quot;: &quot;NYSE MKT&quot;,
&quot;Symbol&quot;: &quot;GT&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;Symbol&quot;: &quot;NDAQ&quot;,
&quot;Volume&quot;:            200,
&quot;Proportion&quot;: 0.0001324332288214 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;Symbol&quot;: &quot;NDAQ&quot;,
&quot;Volume&quot;:            858,
&quot;Proportion&quot;: 0.000568138551644 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;Symbol&quot;: &quot;NDAQ&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;Symbol&quot;: &quot;NDAQ&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;Symbol&quot;: &quot;NDAQ&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;Symbol&quot;: &quot;NDAQ&quot;,
&quot;Volume&quot;:           3141,
&quot;Proportion&quot;: 0.002079863858641 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;Symbol&quot;: &quot;NDAQ&quot;,
&quot;Volume&quot;:        1456605,
&quot;Proportion&quot;: 0.9645145163373 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ&quot;,
&quot;Symbol&quot;: &quot;NDAQ&quot;,
&quot;Volume&quot;:          41439,
&quot;Proportion&quot;: 0.02743950284566 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;Symbol&quot;: &quot;NDAQ&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;Symbol&quot;: &quot;NDAQ&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;Symbol&quot;: &quot;NDAQ&quot;,
&quot;Volume&quot;:            100,
&quot;Proportion&quot;: 6.621661441072e-05 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;Symbol&quot;: &quot;NDAQ&quot;,
&quot;Volume&quot;:           7852,
&quot;Proportion&quot;: 0.00519932856353 
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
&quot;Volume&quot;:            732,
&quot;Proportion&quot;: 0.000261428384694 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;Symbol&quot;: &quot;STLD&quot;,
&quot;Volume&quot;:            100,
&quot;Proportion&quot;: 3.57142602041e-05 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;Symbol&quot;: &quot;STLD&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;Symbol&quot;: &quot;STLD&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;Symbol&quot;: &quot;STLD&quot;,
&quot;Volume&quot;:           2900,
&quot;Proportion&quot;: 0.001035713545919 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;Symbol&quot;: &quot;STLD&quot;,
&quot;Volume&quot;:          39492,
&quot;Proportion&quot;: 0.0141042756398 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;Symbol&quot;: &quot;STLD&quot;,
&quot;Volume&quot;:        2635195,
&quot;Proportion&quot;: 0.9411403991854 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ&quot;,
&quot;Symbol&quot;: &quot;STLD&quot;,
&quot;Volume&quot;:          60623,
&quot;Proportion&quot;: 0.02165105596353 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;Symbol&quot;: &quot;STLD&quot;,
&quot;Volume&quot;:            100,
&quot;Proportion&quot;: 3.57142602041e-05 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;Symbol&quot;: &quot;STLD&quot;,
&quot;Volume&quot;:            400,
&quot;Proportion&quot;: 0.0001428570408164 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;Symbol&quot;: &quot;STLD&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;Symbol&quot;: &quot;STLD&quot;,
&quot;Volume&quot;:          60460,
&quot;Proportion&quot;: 0.0215928417194 
},
{
 &quot;Exchange&quot;: &quot;NYSE MKT&quot;,
&quot;Symbol&quot;: &quot;STLD&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;Symbol&quot;: &quot;TSLA&quot;,
&quot;Volume&quot;:         168190,
&quot;Proportion&quot;: 0.008018475819282 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;Symbol&quot;: &quot;TSLA&quot;,
&quot;Volume&quot;:          54800,
&quot;Proportion&quot;: 0.002612595724458 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;Symbol&quot;: &quot;TSLA&quot;,
&quot;Volume&quot;:           4332,
&quot;Proportion&quot;: 0.0002065285525247 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;Symbol&quot;: &quot;TSLA&quot;,
&quot;Volume&quot;:           1200,
&quot;Proportion&quot;: 5.721012535311e-05 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;Symbol&quot;: &quot;TSLA&quot;,
&quot;Volume&quot;:         235360,
&quot;Proportion&quot;: 0.01122081258592 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;Symbol&quot;: &quot;TSLA&quot;,
&quot;Volume&quot;:        8253449,
&quot;Proportion&quot;: 0.3934840432379 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;Symbol&quot;: &quot;TSLA&quot;,
&quot;Volume&quot;:        5855413,
&quot;Proportion&quot;: 0.2791574264368 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ&quot;,
&quot;Symbol&quot;: &quot;TSLA&quot;,
&quot;Volume&quot;:        1760107,
&quot;Proportion&quot;: 0.0839132850874 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;Symbol&quot;: &quot;TSLA&quot;,
&quot;Volume&quot;:         107713,
&quot;Proportion&quot;: 0.005135228526799 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;Symbol&quot;: &quot;TSLA&quot;,
&quot;Volume&quot;:           1600,
&quot;Proportion&quot;: 7.628016713747e-05 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;Symbol&quot;: &quot;TSLA&quot;,
&quot;Volume&quot;:            400,
&quot;Proportion&quot;: 1.907004178437e-05 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;Symbol&quot;: &quot;TSLA&quot;,
&quot;Volume&quot;:        4532744,
&quot;Proportion&quot;: 0.2160990436946 
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
&quot;Volume&quot;:          66292,
&quot;Proportion&quot;: 0.005072044345576 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;Symbol&quot;: &quot;WFM&quot;,
&quot;Volume&quot;:          16500,
&quot;Proportion&quot;: 0.001262425808574 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;Symbol&quot;: &quot;WFM&quot;,
&quot;Volume&quot;:            600,
&quot;Proportion&quot;: 4.590639303906e-05 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;Symbol&quot;: &quot;WFM&quot;,
&quot;Volume&quot;:           5000,
&quot;Proportion&quot;: 0.0003825532753255 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;Symbol&quot;: &quot;WFM&quot;,
&quot;Volume&quot;:          65552,
&quot;Proportion&quot;: 0.005015426460828 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;Symbol&quot;: &quot;WFM&quot;,
&quot;Volume&quot;:        2782574,
&quot;Proportion&quot;: 0.2128965595071 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;Symbol&quot;: &quot;WFM&quot;,
&quot;Volume&quot;:        6194711,
&quot;Proportion&quot;: 0.473961396549 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ&quot;,
&quot;Symbol&quot;: &quot;WFM&quot;,
&quot;Volume&quot;:         981859,
&quot;Proportion&quot;: 0.07512267527157 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;Symbol&quot;: &quot;WFM&quot;,
&quot;Volume&quot;:          25590,
&quot;Proportion&quot;: 0.001957907663116 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;Symbol&quot;: &quot;WFM&quot;,
&quot;Volume&quot;:            700,
&quot;Proportion&quot;: 5.355745854557e-05 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;Symbol&quot;: &quot;WFM&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;Symbol&quot;: &quot;WFM&quot;,
&quot;Volume&quot;:        2930697,
&quot;Proportion&quot;: 0.2242295472673 
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
&lt;/html&gt; ' scrolling='no' frameBorder='0' seamless class='rChart  nvd3  ' id='iframe-chart1b382e4b1cd6'> </iframe>
 <style>iframe.rChart{ width: 100%; height: 400px;}</style>
 
 We also see some variability among NYSE listed stocks:
 
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
    
    &lt;div id = &#039;chart1b387c7e1018&#039; class = &#039;rChart nvd3&#039;&gt;&lt;/div&gt;    
    &lt;script type=&#039;text/javascript&#039;&gt;
 $(document).ready(function(){
      drawchart1b387c7e1018()
    });
    function drawchart1b387c7e1018(){  
      var opts = {
 &quot;dom&quot;: &quot;chart1b387c7e1018&quot;,
&quot;width&quot;:    800,
&quot;height&quot;:    400,
&quot;x&quot;: &quot;Symbol&quot;,
&quot;y&quot;: &quot;Proportion&quot;,
&quot;group&quot;: &quot;Exchange&quot;,
&quot;type&quot;: &quot;multiBarChart&quot;,
&quot;id&quot;: &quot;chart1b387c7e1018&quot; 
},
        data = [
 {
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;Symbol&quot;: &quot;AMD&quot;,
&quot;Volume&quot;:        1185398,
&quot;Proportion&quot;: 0.0379298994504 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;Symbol&quot;: &quot;AMD&quot;,
&quot;Volume&quot;:          40243,
&quot;Proportion&quot;: 0.001287679702161 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;Symbol&quot;: &quot;AMD&quot;,
&quot;Volume&quot;:            500,
&quot;Proportion&quot;: 1.599880354548e-05 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;Symbol&quot;: &quot;AMD&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;Symbol&quot;: &quot;AMD&quot;,
&quot;Volume&quot;:         248996,
&quot;Proportion&quot;: 0.007967276175219 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;Symbol&quot;: &quot;AMD&quot;,
&quot;Volume&quot;:       19422065,
&quot;Proportion&quot;: 0.6214596047649 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;Symbol&quot;: &quot;AMD&quot;,
&quot;Volume&quot;:          27466,
&quot;Proportion&quot;: 0.0008788462763601 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX&quot;,
&quot;Symbol&quot;: &quot;AMD&quot;,
&quot;Volume&quot;:        2109073,
&quot;Proportion&quot;: 0.06748528918013 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;Symbol&quot;: &quot;AMD&quot;,
&quot;Volume&quot;:          39125,
&quot;Proportion&quot;: 0.001251906377433 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;Symbol&quot;: &quot;AMD&quot;,
&quot;Volume&quot;:          65600,
&quot;Proportion&quot;: 0.002099043025166 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;Symbol&quot;: &quot;AMD&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NYSE&quot;,
&quot;Symbol&quot;: &quot;AMD&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;Symbol&quot;: &quot;AMD&quot;,
&quot;Volume&quot;:        8113871,
&quot;Proportion&quot;: 0.2596244562447 
},
{
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;Symbol&quot;: &quot;BHP&quot;,
&quot;Volume&quot;:          71933,
&quot;Proportion&quot;: 0.008821276232024 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;Symbol&quot;: &quot;BHP&quot;,
&quot;Volume&quot;:            800,
&quot;Proportion&quot;: 9.81054729487e-05 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;Symbol&quot;: &quot;BHP&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;Symbol&quot;: &quot;BHP&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;Symbol&quot;: &quot;BHP&quot;,
&quot;Volume&quot;:           3120,
&quot;Proportion&quot;: 0.0003826113444999 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;Symbol&quot;: &quot;BHP&quot;,
&quot;Volume&quot;:         380894,
&quot;Proportion&quot;: 0.04670973251665 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;Symbol&quot;: &quot;BHP&quot;,
&quot;Volume&quot;:           1300,
&quot;Proportion&quot;: 0.0001594213935416 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX&quot;,
&quot;Symbol&quot;: &quot;BHP&quot;,
&quot;Volume&quot;:         169165,
&quot;Proportion&quot;: 0.02074501541421 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;Symbol&quot;: &quot;BHP&quot;,
&quot;Volume&quot;:            750,
&quot;Proportion&quot;: 9.197388088941e-05 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;Symbol&quot;: &quot;BHP&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;Symbol&quot;: &quot;BHP&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NYSE&quot;,
&quot;Symbol&quot;: &quot;BHP&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;Symbol&quot;: &quot;BHP&quot;,
&quot;Volume&quot;:        7526527,
&quot;Proportion&quot;: 0.9229918637452 
},
{
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;Symbol&quot;: &quot;CVS&quot;,
&quot;Volume&quot;:           6200,
&quot;Proportion&quot;: 0.01631974056877 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;Symbol&quot;: &quot;CVS&quot;,
&quot;Volume&quot;:            100,
&quot;Proportion&quot;: 0.0002632216220769 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;Symbol&quot;: &quot;CVS&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;Symbol&quot;: &quot;CVS&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;Symbol&quot;: &quot;CVS&quot;,
&quot;Volume&quot;:           1663,
&quot;Proportion&quot;: 0.004377375575139 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;Symbol&quot;: &quot;CVS&quot;,
&quot;Volume&quot;:         110376,
&quot;Proportion&quot;: 0.2905334975836 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;Symbol&quot;: &quot;CVS&quot;,
&quot;Volume&quot;:            100,
&quot;Proportion&quot;: 0.0002632216220769 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX&quot;,
&quot;Symbol&quot;: &quot;CVS&quot;,
&quot;Volume&quot;:          60955,
&quot;Proportion&quot;: 0.160446739737 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;Symbol&quot;: &quot;CVS&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;Symbol&quot;: &quot;CVS&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;Symbol&quot;: &quot;CVS&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NYSE&quot;,
&quot;Symbol&quot;: &quot;CVS&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;Symbol&quot;: &quot;CVS&quot;,
&quot;Volume&quot;:         200514,
&quot;Proportion&quot;: 0.5277962032913 
},
{
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;Symbol&quot;: &quot;GE&quot;,
&quot;Volume&quot;:         185261,
&quot;Proportion&quot;: 0.01362689174528 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;Symbol&quot;: &quot;GE&quot;,
&quot;Volume&quot;:           8900,
&quot;Proportion&quot;: 0.0006546404074953 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;Symbol&quot;: &quot;GE&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;Symbol&quot;: &quot;GE&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;Symbol&quot;: &quot;GE&quot;,
&quot;Volume&quot;:          27387,
&quot;Proportion&quot;: 0.002014453577536 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;Symbol&quot;: &quot;GE&quot;,
&quot;Volume&quot;:        5291886,
&quot;Proportion&quot;: 0.3892452143212 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;Symbol&quot;: &quot;GE&quot;,
&quot;Volume&quot;:           8550,
&quot;Proportion&quot;: 0.0006288961218072 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX&quot;,
&quot;Symbol&quot;: &quot;GE&quot;,
&quot;Volume&quot;:         687581,
&quot;Proportion&quot;: 0.05057509056472 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;Symbol&quot;: &quot;GE&quot;,
&quot;Volume&quot;:           4000,
&quot;Proportion&quot;: 0.000294220407863 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;Symbol&quot;: &quot;GE&quot;,
&quot;Volume&quot;:           7800,
&quot;Proportion&quot;: 0.0005737297953329 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;Symbol&quot;: &quot;GE&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NYSE&quot;,
&quot;Symbol&quot;: &quot;GE&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;Symbol&quot;: &quot;GE&quot;,
&quot;Volume&quot;:        7373885,
&quot;Proportion&quot;: 0.5423868630588 
},
{
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;Symbol&quot;: &quot;LTM&quot;,
&quot;Volume&quot;:            200,
&quot;Proportion&quot;: 0.002580045924817 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;Symbol&quot;: &quot;LTM&quot;,
&quot;Volume&quot;:            100,
&quot;Proportion&quot;: 0.001290022962409 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;Symbol&quot;: &quot;LTM&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;Symbol&quot;: &quot;LTM&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;Symbol&quot;: &quot;LTM&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;Symbol&quot;: &quot;LTM&quot;,
&quot;Volume&quot;:          11496,
&quot;Proportion&quot;: 0.1483010397585 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;Symbol&quot;: &quot;LTM&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX&quot;,
&quot;Symbol&quot;: &quot;LTM&quot;,
&quot;Volume&quot;:           6877,
&quot;Proportion&quot;: 0.08871487912485 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;Symbol&quot;: &quot;LTM&quot;,
&quot;Volume&quot;:            100,
&quot;Proportion&quot;: 0.001290022962409 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;Symbol&quot;: &quot;LTM&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;Symbol&quot;: &quot;LTM&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NYSE&quot;,
&quot;Symbol&quot;: &quot;LTM&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;Symbol&quot;: &quot;LTM&quot;,
&quot;Volume&quot;:          58745,
&quot;Proportion&quot;: 0.757823989267 
},
{
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;Symbol&quot;: &quot;LUV&quot;,
&quot;Volume&quot;:           4418,
&quot;Proportion&quot;: 0.005442522137194 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;Symbol&quot;: &quot;LUV&quot;,
&quot;Volume&quot;:            100,
&quot;Proportion&quot;: 0.0001231897269623 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;Symbol&quot;: &quot;LUV&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;Symbol&quot;: &quot;LUV&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;Symbol&quot;: &quot;LUV&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;Symbol&quot;: &quot;LUV&quot;,
&quot;Volume&quot;:         443600,
&quot;Proportion&quot;: 0.5464696288047 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;Symbol&quot;: &quot;LUV&quot;,
&quot;Volume&quot;:            200,
&quot;Proportion&quot;: 0.0002463794539246 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX&quot;,
&quot;Symbol&quot;: &quot;LUV&quot;,
&quot;Volume&quot;:          49417,
&quot;Proportion&quot;: 0.06087666737295 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;Symbol&quot;: &quot;LUV&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;Symbol&quot;: &quot;LUV&quot;,
&quot;Volume&quot;:            100,
&quot;Proportion&quot;: 0.0001231897269623 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;Symbol&quot;: &quot;LUV&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NYSE&quot;,
&quot;Symbol&quot;: &quot;LUV&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;Symbol&quot;: &quot;LUV&quot;,
&quot;Volume&quot;:         313921,
&quot;Proportion&quot;: 0.3867184227773 
},
{
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;Symbol&quot;: &quot;WSM&quot;,
&quot;Volume&quot;:           4741,
&quot;Proportion&quot;: 0.003441587384089 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;Symbol&quot;: &quot;WSM&quot;,
&quot;Volume&quot;:            400,
&quot;Proportion&quot;: 0.0002903680560294 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;Symbol&quot;: &quot;WSM&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;Symbol&quot;: &quot;WSM&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;Symbol&quot;: &quot;WSM&quot;,
&quot;Volume&quot;:           7179,
&quot;Proportion&quot;: 0.005211380685588 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;Symbol&quot;: &quot;WSM&quot;,
&quot;Volume&quot;:         560880,
&quot;Proportion&quot;: 0.4071540881645 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;Symbol&quot;: &quot;WSM&quot;,
&quot;Volume&quot;:           1200,
&quot;Proportion&quot;: 0.0008711041680883 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX&quot;,
&quot;Symbol&quot;: &quot;WSM&quot;,
&quot;Volume&quot;:         132016,
&quot;Proportion&quot;: 0.09583307321195 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;Symbol&quot;: &quot;WSM&quot;,
&quot;Volume&quot;:           1800,
&quot;Proportion&quot;: 0.001306656252132 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;Symbol&quot;: &quot;WSM&quot;,
&quot;Volume&quot;:            300,
&quot;Proportion&quot;: 0.0002177760420221 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;Symbol&quot;: &quot;WSM&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NYSE&quot;,
&quot;Symbol&quot;: &quot;WSM&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;Symbol&quot;: &quot;WSM&quot;,
&quot;Volume&quot;:         669046,
&quot;Proportion&quot;: 0.4856739660356 
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
&lt;/html&gt; ' scrolling='no' frameBorder='0' seamless class='rChart  nvd3  ' id='iframe-chart1b387c7e1018'> </iframe>
 <style>iframe.rChart{ width: 100%; height: 400px;}</style>
 
 Finally, we see some variability among NYSE MKT stocks:
 
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
    
    &lt;div id = &#039;chart1b3835735e15&#039; class = &#039;rChart nvd3&#039;&gt;&lt;/div&gt;    
    &lt;script type=&#039;text/javascript&#039;&gt;
 $(document).ready(function(){
      drawchart1b3835735e15()
    });
    function drawchart1b3835735e15(){  
      var opts = {
 &quot;dom&quot;: &quot;chart1b3835735e15&quot;,
&quot;width&quot;:    800,
&quot;height&quot;:    400,
&quot;x&quot;: &quot;Symbol&quot;,
&quot;y&quot;: &quot;Proportion&quot;,
&quot;group&quot;: &quot;Exchange&quot;,
&quot;type&quot;: &quot;multiBarChart&quot;,
&quot;id&quot;: &quot;chart1b3835735e15&quot; 
},
        data = [
 {
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;Symbol&quot;: &quot;CCF&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;Symbol&quot;: &quot;CCF&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;Symbol&quot;: &quot;CCF&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
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
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;Symbol&quot;: &quot;CCF&quot;,
&quot;Volume&quot;:            500,
&quot;Proportion&quot;: 0.5555555555556 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;Symbol&quot;: &quot;CCF&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX&quot;,
&quot;Symbol&quot;: &quot;CCF&quot;,
&quot;Volume&quot;:            100,
&quot;Proportion&quot;: 0.1111111111111 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;Symbol&quot;: &quot;CCF&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;Symbol&quot;: &quot;CCF&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;Symbol&quot;: &quot;CCF&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;Symbol&quot;: &quot;CCF&quot;,
&quot;Volume&quot;:            300,
&quot;Proportion&quot;: 0.3333333333333 
},
{
 &quot;Exchange&quot;: &quot;NYSE MKT&quot;,
&quot;Symbol&quot;: &quot;CCF&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;Symbol&quot;: &quot;LIQT&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;: null 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;Symbol&quot;: &quot;LIQT&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;: null 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;Symbol&quot;: &quot;LIQT&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;: null 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;Symbol&quot;: &quot;LIQT&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;: null 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;Symbol&quot;: &quot;LIQT&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;: null 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;Symbol&quot;: &quot;LIQT&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;: null 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;Symbol&quot;: &quot;LIQT&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;: null 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX&quot;,
&quot;Symbol&quot;: &quot;LIQT&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;: null 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;Symbol&quot;: &quot;LIQT&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;: null 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;Symbol&quot;: &quot;LIQT&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;: null 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;Symbol&quot;: &quot;LIQT&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;: null 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;Symbol&quot;: &quot;LIQT&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;: null 
},
{
 &quot;Exchange&quot;: &quot;NYSE MKT&quot;,
&quot;Symbol&quot;: &quot;LIQT&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;: null 
},
{
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;Symbol&quot;: &quot;ONP&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;Symbol&quot;: &quot;ONP&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;Symbol&quot;: &quot;ONP&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
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
&quot;Volume&quot;:            652,
&quot;Proportion&quot;: 0.09053040821994 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;Symbol&quot;: &quot;ONP&quot;,
&quot;Volume&quot;:           1500,
&quot;Proportion&quot;: 0.2082754790336 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;Symbol&quot;: &quot;ONP&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX&quot;,
&quot;Symbol&quot;: &quot;ONP&quot;,
&quot;Volume&quot;:           1100,
&quot;Proportion&quot;: 0.1527353512913 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;Symbol&quot;: &quot;ONP&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;Symbol&quot;: &quot;ONP&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;Symbol&quot;: &quot;ONP&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;Symbol&quot;: &quot;ONP&quot;,
&quot;Volume&quot;:           3950,
&quot;Proportion&quot;: 0.5484587614552 
},
{
 &quot;Exchange&quot;: &quot;NYSE MKT&quot;,
&quot;Symbol&quot;: &quot;ONP&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;:              0 
},
{
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;Symbol&quot;: &quot;ONVO&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;: null 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;Symbol&quot;: &quot;ONVO&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;: null 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;Symbol&quot;: &quot;ONVO&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;: null 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;Symbol&quot;: &quot;ONVO&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;: null 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;Symbol&quot;: &quot;ONVO&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;: null 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;Symbol&quot;: &quot;ONVO&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;: null 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;Symbol&quot;: &quot;ONVO&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;: null 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX&quot;,
&quot;Symbol&quot;: &quot;ONVO&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;: null 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;Symbol&quot;: &quot;ONVO&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;: null 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;Symbol&quot;: &quot;ONVO&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;: null 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;Symbol&quot;: &quot;ONVO&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;: null 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;Symbol&quot;: &quot;ONVO&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;: null 
},
{
 &quot;Exchange&quot;: &quot;NYSE MKT&quot;,
&quot;Symbol&quot;: &quot;ONVO&quot;,
&quot;Volume&quot;:              0,
&quot;Proportion&quot;: null 
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
&lt;/html&gt; ' scrolling='no' frameBorder='0' seamless class='rChart  nvd3  ' id='iframe-chart1b3835735e15'> </iframe>
 <style>iframe.rChart{ width: 100%; height: 400px;}</style>

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
