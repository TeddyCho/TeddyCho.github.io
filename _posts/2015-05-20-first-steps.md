---
layout: post
title: First Steps
---
hi

<iframe src = ' https://raw.githubusercontent.com/TeddyCho/TeddyCho.github.io/master/_posts/img/nyseReg.html ' scrolling='no' frameBorder='0' seamless class='rChart  nvd3  ' id='iframe-chart1b3823a857f0'> </iframe>
 <style>iframe.rChart{ width: 100%; height: 400px;}</style>
 
hi


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

Back in the US from [hiking about](http://LegDays.com), I am on a new journey towards becoming an academic.

This post marks my first public step.

So let's do this!

<img style="float: center" src="https://github.com/TeddyCho/TeddyCho.github.io/blob/master/_posts/img/IMG_7024-EFFECTS.jpg?raw=true" width="500" height="500" />
