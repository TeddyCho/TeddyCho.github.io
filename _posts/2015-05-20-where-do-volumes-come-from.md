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
    <tr>      <th>Timeframe</th>      <th>Symbols</th>    </tr>
  </thead>
  <tbody>
    <tr>      <td>01-Jan-2014 to 31-Dec-2014</td>      <td>BAC, GOOG, BHP, BRKA, FE, RSH, SLV, T, XOM</td>    </tr>
  </tbody>
</table>
Transforming the above data (64209422 rows) to per-timeOfDay-per-day exchange volumes took 495 seconds on a 2.4 GHz/4GB laptop. The raw output from the code is [here](https://github.com/TeddyCho/TeddyCho.github.io/blob/master/_posts/img/breakdown1.csv).

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
    
    &lt;div id = &#039;chart1504297d158d&#039; class = &#039;rChart nvd3&#039;&gt;&lt;/div&gt;    
    &lt;script type=&#039;text/javascript&#039;&gt;
 $(document).ready(function(){
      drawchart1504297d158d()
    });
    function drawchart1504297d158d(){  
      var opts = {
 &quot;dom&quot;: &quot;chart1504297d158d&quot;,
&quot;width&quot;:    800,
&quot;height&quot;:    400,
&quot;x&quot;: &quot;Common&quot;,
&quot;y&quot;: &quot;Volume&quot;,
&quot;group&quot;: &quot;Exchange&quot;,
&quot;type&quot;: &quot;multiBarChart&quot;,
&quot;id&quot;: &quot;chart1504297d158d&quot; 
},
        data = [
 {
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;Volume&quot;:     1569844265,
&quot;Common&quot;: &quot;Aggregate&quot; 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;Volume&quot;:      922446499,
&quot;Common&quot;: &quot;Aggregate&quot; 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;Volume&quot;:       22517429,
&quot;Common&quot;: &quot;Aggregate&quot; 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;Volume&quot;:      181158359,
&quot;Common&quot;: &quot;Aggregate&quot; 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;Volume&quot;:      915651685,
&quot;Common&quot;: &quot;Aggregate&quot; 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;Volume&quot;:     2053407256,
&quot;Common&quot;: &quot;Aggregate&quot; 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;Volume&quot;:    10064238734,
&quot;Common&quot;: &quot;Aggregate&quot; 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ&quot;,
&quot;Volume&quot;:      148971605,
&quot;Common&quot;: &quot;Aggregate&quot; 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX&quot;,
&quot;Volume&quot;:     2522686933,
&quot;Common&quot;: &quot;Aggregate&quot; 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;Volume&quot;:      998253900,
&quot;Common&quot;: &quot;Aggregate&quot; 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;Volume&quot;:      136601845,
&quot;Common&quot;: &quot;Aggregate&quot; 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;Volume&quot;:       65506674,
&quot;Common&quot;: &quot;Aggregate&quot; 
},
{
 &quot;Exchange&quot;: &quot;NYSE&quot;,
&quot;Volume&quot;:     4794287787,
&quot;Common&quot;: &quot;Aggregate&quot; 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;Volume&quot;:     1893378717,
&quot;Common&quot;: &quot;Aggregate&quot; 
},
{
 &quot;Exchange&quot;: &quot;NYSE MKT&quot;,
&quot;Volume&quot;:        1493112,
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
&lt;/html&gt; ' scrolling='no' frameBorder='0' seamless class='rChart  nvd3  ' id='iframe-chart1504297d158d'> </iframe>
 <style>iframe.rChart{ width: 100%; height: 400px;}</style>
 
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

Most symbols had similar profiles in exchange market share. To illustrate, stocks BHP, FE, and XOM were chosen since their volumes were at comparable scales:

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
    
    &lt;div id = &#039;chart150461876fa3&#039; class = &#039;rChart nvd3&#039;&gt;&lt;/div&gt;    
    &lt;script type=&#039;text/javascript&#039;&gt;
 $(document).ready(function(){
      drawchart150461876fa3()
    });
    function drawchart150461876fa3(){  
      var opts = {
 &quot;dom&quot;: &quot;chart150461876fa3&quot;,
&quot;width&quot;:    800,
&quot;height&quot;:    400,
&quot;x&quot;: &quot;Symbol&quot;,
&quot;y&quot;: &quot;Volume&quot;,
&quot;group&quot;: &quot;Exchange&quot;,
&quot;type&quot;: &quot;multiBarChart&quot;,
&quot;id&quot;: &quot;chart150461876fa3&quot; 
},
        data = [
 {
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;Symbol&quot;: &quot;BHP&quot;,
&quot;Volume&quot;:       31640647 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;Symbol&quot;: &quot;BHP&quot;,
&quot;Volume&quot;:        6800526 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;Symbol&quot;: &quot;BHP&quot;,
&quot;Volume&quot;:          93873 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;Symbol&quot;: &quot;BHP&quot;,
&quot;Volume&quot;:        2219584 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;Symbol&quot;: &quot;BHP&quot;,
&quot;Volume&quot;:       10329686 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;Symbol&quot;: &quot;BHP&quot;,
&quot;Volume&quot;:       18623066 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;Symbol&quot;: &quot;BHP&quot;,
&quot;Volume&quot;:      117420976 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX&quot;,
&quot;Symbol&quot;: &quot;BHP&quot;,
&quot;Volume&quot;:       39581976 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;Symbol&quot;: &quot;BHP&quot;,
&quot;Volume&quot;:        6306904 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;Symbol&quot;: &quot;BHP&quot;,
&quot;Volume&quot;:        1231276 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;Symbol&quot;: &quot;BHP&quot;,
&quot;Volume&quot;:         323776 
},
{
 &quot;Exchange&quot;: &quot;NYSE&quot;,
&quot;Symbol&quot;: &quot;BHP&quot;,
&quot;Volume&quot;:       85662564 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;Symbol&quot;: &quot;BHP&quot;,
&quot;Volume&quot;:       39518621 
},
{
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;Symbol&quot;: &quot;FE&quot;,
&quot;Volume&quot;:       57078603 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;Symbol&quot;: &quot;FE&quot;,
&quot;Volume&quot;:       16980139 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;Symbol&quot;: &quot;FE&quot;,
&quot;Volume&quot;:         940649 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;Symbol&quot;: &quot;FE&quot;,
&quot;Volume&quot;:         489515 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;Symbol&quot;: &quot;FE&quot;,
&quot;Volume&quot;:       15384820 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;Symbol&quot;: &quot;FE&quot;,
&quot;Volume&quot;:       32780099 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;Symbol&quot;: &quot;FE&quot;,
&quot;Volume&quot;:      225313071 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX&quot;,
&quot;Symbol&quot;: &quot;FE&quot;,
&quot;Volume&quot;:      106892442 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;Symbol&quot;: &quot;FE&quot;,
&quot;Volume&quot;:       17073784 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;Symbol&quot;: &quot;FE&quot;,
&quot;Volume&quot;:        2031776 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;Symbol&quot;: &quot;FE&quot;,
&quot;Volume&quot;:         961314 
},
{
 &quot;Exchange&quot;: &quot;NYSE&quot;,
&quot;Symbol&quot;: &quot;FE&quot;,
&quot;Volume&quot;:      164674613 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;Symbol&quot;: &quot;FE&quot;,
&quot;Volume&quot;:       44860834 
},
{
 &quot;Exchange&quot;: &quot;BATS&quot;,
&quot;Symbol&quot;: &quot;XOM&quot;,
&quot;Volume&quot;:      140789748 
},
{
 &quot;Exchange&quot;: &quot;BATS Y&quot;,
&quot;Symbol&quot;: &quot;XOM&quot;,
&quot;Volume&quot;:       35080663 
},
{
 &quot;Exchange&quot;: &quot;CBOE&quot;,
&quot;Symbol&quot;: &quot;XOM&quot;,
&quot;Volume&quot;:         461497 
},
{
 &quot;Exchange&quot;: &quot;Chicago&quot;,
&quot;Symbol&quot;: &quot;XOM&quot;,
&quot;Volume&quot;:       14584730 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge A&quot;,
&quot;Symbol&quot;: &quot;XOM&quot;,
&quot;Volume&quot;:       38287024 
},
{
 &quot;Exchange&quot;: &quot;Direct Edge X&quot;,
&quot;Symbol&quot;: &quot;XOM&quot;,
&quot;Volume&quot;:       91720860 
},
{
 &quot;Exchange&quot;: &quot;FINRA&quot;,
&quot;Symbol&quot;: &quot;XOM&quot;,
&quot;Volume&quot;:      611924090 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX&quot;,
&quot;Symbol&quot;: &quot;XOM&quot;,
&quot;Volume&quot;:      312281974 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX BX&quot;,
&quot;Symbol&quot;: &quot;XOM&quot;,
&quot;Volume&quot;:       31507411 
},
{
 &quot;Exchange&quot;: &quot;NASDAQ OMX PSX&quot;,
&quot;Symbol&quot;: &quot;XOM&quot;,
&quot;Volume&quot;:        7696102 
},
{
 &quot;Exchange&quot;: &quot;National&quot;,
&quot;Symbol&quot;: &quot;XOM&quot;,
&quot;Volume&quot;:        3782286 
},
{
 &quot;Exchange&quot;: &quot;NYSE&quot;,
&quot;Symbol&quot;: &quot;XOM&quot;,
&quot;Volume&quot;:      533944804 
},
{
 &quot;Exchange&quot;: &quot;NYSE Arca SM&quot;,
&quot;Symbol&quot;: &quot;XOM&quot;,
&quot;Volume&quot;:      181008313 
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
&lt;/html&gt; ' scrolling='no' frameBorder='0' seamless class='rChart  nvd3  ' id='iframe-chart150461876fa3'> </iframe>
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
    
    &lt;div id = &#039;chart150422502c52&#039; class = &#039;rChart nvd3&#039;&gt;&lt;/div&gt;    
    &lt;script type=&#039;text/javascript&#039;&gt;
 $(document).ready(function(){
      drawchart150422502c52()
    });
    function drawchart150422502c52(){  
      var opts = {
 &quot;dom&quot;: &quot;chart150422502c52&quot;,
&quot;width&quot;:    800,
&quot;height&quot;:    400,
&quot;x&quot;: &quot;Symbol&quot;,
&quot;y&quot;: &quot;Volume&quot;,
&quot;group&quot;: &quot;Exchange&quot;,
&quot;type&quot;: &quot;multiBarChart&quot;,
&quot;id&quot;: &quot;chart150422502c52&quot; 
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
&lt;/html&gt; ' scrolling='no' frameBorder='0' seamless class='rChart  nvd3  ' id='iframe-chart150422502c52'> </iframe>
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
    
    &lt;div id = &#039;chart15041d063979&#039; class = &#039;rChart nvd3&#039;&gt;&lt;/div&gt;    
    &lt;script type=&#039;text/javascript&#039;&gt;
 $(document).ready(function(){
      drawchart15041d063979()
    });
    function drawchart15041d063979(){  
      var opts = {
 &quot;dom&quot;: &quot;chart15041d063979&quot;,
&quot;width&quot;:    800,
&quot;height&quot;:    400,
&quot;x&quot;: &quot;Symbol&quot;,
&quot;y&quot;: &quot;Volume&quot;,
&quot;group&quot;: &quot;Exchange&quot;,
&quot;type&quot;: &quot;multiBarChart&quot;,
&quot;id&quot;: &quot;chart15041d063979&quot; 
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
&lt;/html&gt; ' scrolling='no' frameBorder='0' seamless class='rChart  nvd3  ' id='iframe-chart15041d063979'> </iframe>
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
