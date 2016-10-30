---
title       : Pe'ah Garden stats
subtitle    : Results for 2016
author      : Scott Gaul
job         : Pe'ah stats person
framework   : minimal      # 
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
ext_widgets : {rCharts: ["libraries/nvd3"]} 
mode        : selfcontained # {standalone, draft}
---

## 2016 overall results

We had great results again in 2016! 

We are on track for a great harvest again in 2016, even more than [close to 2015, which was the previous highest yield ever](http://sgaul.github.io/peah2015/).    

While we are still harvesting, gardeners so far have distributed 2,400 pounds of vegetables or about 235,000 calories - roughly three months of food for an adult. This is on track with last year's totals, which were the previous highest ever.





<div id = 'chart1' class = 'rChart nvd3'></div>
<script type='text/javascript'>
 $(document).ready(function(){
      drawchart1()
    });
    function drawchart1(){  
      var opts = {
 "dom": "chart1",
"width":    500,
"height":    300,
"x": "Year",
"y": "Calories",
"type": "discreteBarChart",
"id": "chart1" 
},
        data = [
 {
 "Year": 2002,
"Pounds":        1273.25,
"Calories": 114403.9329167 
},
{
 "Year": 2003,
"Pounds":          778.5,
"Calories":       86920.57 
},
{
 "Year": 2004,
"Pounds":        1302.25,
"Calories":      140183.85 
},
{
 "Year": 2005,
"Pounds":         1392.5,
"Calories":      151554.28 
},
{
 "Year": 2006,
"Pounds":        1321.25,
"Calories":     134382.865 
},
{
 "Year": 2007,
"Pounds":        1686.25,
"Calories":  153063.073334 
},
{
 "Year": 2008,
"Pounds":            898,
"Calories":    90317.34125 
},
{
 "Year": 2009,
"Pounds":           1028,
"Calories": 100385.8316667 
},
{
 "Year": 2010,
"Pounds":         911.75,
"Calories":      84708.455 
},
{
 "Year": 2011,
"Pounds":           1269,
"Calories":      147313.92 
},
{
 "Year": 2012,
"Pounds":        1901.23,
"Calories":    164506.3552 
},
{
 "Year": 2013,
"Pounds":            608,
"Calories":      67887.755 
},
{
 "Year": 2014,
"Pounds":           2634,
"Calories":      260500.66 
},
{
 "Year": 2015,
"Pounds":        2580.35,
"Calories":     240780.035 
},
{
 "Year": 2016,
"Pounds":         2387.2,
"Calories":     234271.945 
} 
]
  
      if(!(opts.type==="pieChart" || opts.type==="sparklinePlus" || opts.type==="bulletChart")) {
        var data = d3.nest()
          .key(function(d){
            //return opts.group === undefined ? 'main' : d[opts.group]
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
          
        if (opts.type != "bulletChart"){
          chart
            .x(function(d) { return d[opts.x] })
            .y(function(d) { return d[opts.y] })
        }
          
         
        chart
  .forceY([      0, 1.7e+05 ])
  .margin({
 "left":     80 
})
          
        chart.xAxis
  .axisLabel("Year")

        
        
        chart.yAxis
  .tickFormat(function(d) {return d3.format(',.0f')(d)})
  .axisLabel("Calories")
      
       d3.select("#" + opts.id)
        .append('svg')
        .datum(data)
        .transition().duration(500)
        .call(chart);

       nv.utils.windowResize(chart.update);
       return chart;
      });
    };
</script>

Here is the same result in pounds harvested. 


<div id = 'chart2' class = 'rChart nvd3'></div>
<script type='text/javascript'>
 $(document).ready(function(){
      drawchart2()
    });
    function drawchart2(){  
      var opts = {
 "dom": "chart2",
"width":    500,
"height":    300,
"x": "Year",
"y": "Pounds",
"type": "discreteBarChart",
"id": "chart2" 
},
        data = [
 {
 "Year": 2002,
"Pounds":        1273.25,
"Calories": 114403.9329167 
},
{
 "Year": 2003,
"Pounds":          778.5,
"Calories":       86920.57 
},
{
 "Year": 2004,
"Pounds":        1302.25,
"Calories":      140183.85 
},
{
 "Year": 2005,
"Pounds":         1392.5,
"Calories":      151554.28 
},
{
 "Year": 2006,
"Pounds":        1321.25,
"Calories":     134382.865 
},
{
 "Year": 2007,
"Pounds":        1686.25,
"Calories":  153063.073334 
},
{
 "Year": 2008,
"Pounds":            898,
"Calories":    90317.34125 
},
{
 "Year": 2009,
"Pounds":           1028,
"Calories": 100385.8316667 
},
{
 "Year": 2010,
"Pounds":         911.75,
"Calories":      84708.455 
},
{
 "Year": 2011,
"Pounds":           1269,
"Calories":      147313.92 
},
{
 "Year": 2012,
"Pounds":        1901.23,
"Calories":    164506.3552 
},
{
 "Year": 2013,
"Pounds":            608,
"Calories":      67887.755 
},
{
 "Year": 2014,
"Pounds":           2634,
"Calories":      260500.66 
},
{
 "Year": 2015,
"Pounds":        2580.35,
"Calories":     240780.035 
},
{
 "Year": 2016,
"Pounds":         2387.2,
"Calories":     234271.945 
} 
]
  
      if(!(opts.type==="pieChart" || opts.type==="sparklinePlus" || opts.type==="bulletChart")) {
        var data = d3.nest()
          .key(function(d){
            //return opts.group === undefined ? 'main' : d[opts.group]
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
          
        if (opts.type != "bulletChart"){
          chart
            .x(function(d) { return d[opts.x] })
            .y(function(d) { return d[opts.y] })
        }
          
         
        chart
  .forceY([      0,   1700 ])
  .margin({
 "left":     80 
})
          
        chart.xAxis
  .axisLabel("Year")

        
        
        chart.yAxis
  .tickFormat(function(d) {return d3.format(',.0f')(d)})
  .axisLabel("Pounds")
      
       d3.select("#" + opts.id)
        .append('svg')
        .datum(data)
        .transition().duration(500)
        .call(chart);

       nv.utils.windowResize(chart.update);
       return chart;
      });
    };
</script>

## 2016 individual results

We distributed 29 different kinds of vegetables this year - more than most years - with tomatoes, zucchini andsquash yielding the most (over 250 lbs of each). 

![plot of chunk unnamed-chunk-1](assets/fig/unnamed-chunk-1-1.svg) 

The results by calories are similar, with a couple of high-calorie crops like beets and kale having more of an impact: 

![plot of chunk unnamed-chunk-2](assets/fig/unnamed-chunk-2-1.svg) 

The results by plot are here - congratulations to Melinda, Betsy, Bobbi and everyone else that made this such a great year!

![plot of chunk unnamed-chunk-3](assets/fig/unnamed-chunk-3-1.svg) 

Individual results for the year are listed in the table below. 

<!-- html table generated in R 3.2.1 by xtable 1.7-4 package -->
<!-- Sun Oct 30 06:46:23 2016 -->
<table border=1>
<tr> <th> Name </th> <th> Crop </th> <th> Pounds </th> <th> Calories </th>  </tr>
  <tr> <td> Avi / Michelle </td> <td> beets </td> <td align="right"> 2 </td> <td align="right"> 293 </td> </tr>
  <tr> <td> Avi / Michelle </td> <td> cabbage </td> <td align="right"> 1 </td> <td align="right"> 114 </td> </tr>
  <tr> <td> Avi / Michelle </td> <td> collards </td> <td align="right"> 6 </td> <td align="right"> 817 </td> </tr>
  <tr> <td> Avi / Michelle </td> <td> cucumbers </td> <td align="right"> 62 </td> <td align="right"> 4256 </td> </tr>
  <tr> <td> Avi / Michelle </td> <td> kale </td> <td align="right"> 18 </td> <td align="right"> 4143 </td> </tr>
  <tr> <td> Avi / Michelle </td> <td> lettuce </td> <td align="right"> 36 </td> <td align="right"> 2486 </td> </tr>
  <tr> <td> Avi / Michelle </td> <td> tomatoes </td> <td align="right"> 17 </td> <td align="right"> 1175 </td> </tr>
  <tr> <td> Community </td> <td> cabbage </td> <td align="right"> 5 </td> <td align="right"> 568 </td> </tr>
  <tr> <td> Community </td> <td> collards </td> <td align="right"> 14 </td> <td align="right"> 1839 </td> </tr>
  <tr> <td> Community </td> <td> kale </td> <td align="right"> 6 </td> <td align="right"> 1476 </td> </tr>
  <tr> <td> Community </td> <td> lettuce </td> <td align="right"> 18 </td> <td align="right"> 1226 </td> </tr>
  <tr> <td> Community </td> <td> squash </td> <td align="right"> 26 </td> <td align="right"> 1889 </td> </tr>
  <tr> <td> Community </td> <td> tomatoes </td> <td align="right"> 31 </td> <td align="right"> 2111 </td> </tr>
  <tr> <td> Community </td> <td> watermelon </td> <td align="right"> 14 </td> <td align="right"> 1907 </td> </tr>
  <tr> <td> Community </td> <td> zucchini </td> <td align="right"> 33 </td> <td align="right"> 2379 </td> </tr>
  <tr> <td> Dan / Masha </td> <td> arugula </td> <td align="right"> 1 </td> <td align="right"> 114 </td> </tr>
  <tr> <td> Dan / Masha </td> <td> squash </td> <td align="right"> 137 </td> <td align="right"> 9970 </td> </tr>
  <tr> <td> Dan / Masha </td> <td> swiss chard </td> <td align="right"> 8 </td> <td align="right"> 690 </td> </tr>
  <tr> <td> Dan / Masha </td> <td> tomatoes </td> <td align="right"> 2 </td> <td align="right"> 170 </td> </tr>
  <tr> <td> Dan / Masha </td> <td> turnip greens </td> <td align="right"> 12 </td> <td align="right"> 1525 </td> </tr>
  <tr> <td> Dan / Masha </td> <td> turnips </td> <td align="right"> 48 </td> <td align="right"> 6070 </td> </tr>
  <tr> <td> Holly / Deb </td> <td> cabbage </td> <td align="right"> 2 </td> <td align="right"> 227 </td> </tr>
  <tr> <td> Holly / Deb </td> <td> herbs </td> <td align="right"> 0 </td> <td align="right"> 82 </td> </tr>
  <tr> <td> Holly / Deb </td> <td> kale </td> <td align="right"> 7 </td> <td align="right"> 1589 </td> </tr>
  <tr> <td> Holly / Deb </td> <td> lettuce </td> <td align="right"> 16 </td> <td align="right"> 1090 </td> </tr>
  <tr> <td> Holly / Deb </td> <td> squash </td> <td align="right"> 7 </td> <td align="right"> 508 </td> </tr>
  <tr> <td> Holly / Deb </td> <td> tomatoes </td> <td align="right"> 152 </td> <td align="right"> 10317 </td> </tr>
  <tr> <td> Jen </td> <td> basil </td> <td align="right"> 0 </td> <td align="right"> 26 </td> </tr>
  <tr> <td> Jen </td> <td> broccoli </td> <td align="right"> 68 </td> <td align="right"> 10419 </td> </tr>
  <tr> <td> Jen </td> <td> carrots </td> <td align="right"> 18 </td> <td align="right"> 3257 </td> </tr>
  <tr> <td> Jen </td> <td> cucumbers </td> <td align="right"> 5 </td> <td align="right"> 340 </td> </tr>
  <tr> <td> Jen </td> <td> kale </td> <td align="right"> 2 </td> <td align="right"> 454 </td> </tr>
  <tr> <td> Jen </td> <td> peppers </td> <td align="right"> 4 </td> <td align="right"> 409 </td> </tr>
  <tr> <td> Jen </td> <td> radishes </td> <td align="right"> 21 </td> <td align="right"> 1525 </td> </tr>
  <tr> <td> Jen </td> <td> tomatoes </td> <td align="right"> 23 </td> <td align="right"> 1566 </td> </tr>
  <tr> <td> Katherine </td> <td> basil </td> <td align="right"> 2 </td> <td align="right"> 157 </td> </tr>
  <tr> <td> Katherine </td> <td> beans </td> <td align="right"> 8 </td> <td align="right"> 1196 </td> </tr>
  <tr> <td> Katherine </td> <td> collards </td> <td align="right"> 2 </td> <td align="right"> 238 </td> </tr>
  <tr> <td> Katherine </td> <td> cucumbers </td> <td align="right"> 8 </td> <td align="right"> 511 </td> </tr>
  <tr> <td> Katherine </td> <td> kale </td> <td align="right"> 12 </td> <td align="right"> 2724 </td> </tr>
  <tr> <td> Katherine </td> <td> peppers </td> <td align="right"> 35 </td> <td align="right"> 3155 </td> </tr>
  <tr> <td> Katherine </td> <td> squash </td> <td align="right"> 2 </td> <td align="right"> 163 </td> </tr>
  <tr> <td> Katherine </td> <td> tomatoes </td> <td align="right"> 1 </td> <td align="right"> 51 </td> </tr>
  <tr> <td> Kelly </td> <td> basil </td> <td align="right"> 1 </td> <td align="right"> 104 </td> </tr>
  <tr> <td> Kelly </td> <td> beans </td> <td align="right"> 4 </td> <td align="right"> 563 </td> </tr>
  <tr> <td> Kelly </td> <td> cucumbers </td> <td align="right"> 3 </td> <td align="right"> 204 </td> </tr>
  <tr> <td> Kelly </td> <td> kale </td> <td align="right"> 54 </td> <td align="right"> 12258 </td> </tr>
  <tr> <td> Kelly </td> <td> onions </td> <td align="right"> 5 </td> <td align="right"> 908 </td> </tr>
  <tr> <td> Kelly </td> <td> radishes </td> <td align="right"> 12 </td> <td align="right"> 872 </td> </tr>
  <tr> <td> Kelly </td> <td> spinach </td> <td align="right"> 6 </td> <td align="right"> 627 </td> </tr>
  <tr> <td> Kelly </td> <td> tomatoes </td> <td align="right"> 29 </td> <td align="right"> 1975 </td> </tr>
  <tr> <td> Kelly </td> <td> watermelon </td> <td align="right"> 3 </td> <td align="right"> 409 </td> </tr>
  <tr> <td> Larry / Don </td> <td> beans </td> <td align="right"> 44 </td> <td align="right"> 6263 </td> </tr>
  <tr> <td> Larry / Don </td> <td> beets </td> <td align="right"> 3 </td> <td align="right"> 586 </td> </tr>
  <tr> <td> Larry / Don </td> <td> cabbage </td> <td align="right"> 14 </td> <td align="right"> 1646 </td> </tr>
  <tr> <td> Larry / Don </td> <td> carrots </td> <td align="right"> 4 </td> <td align="right"> 745 </td> </tr>
  <tr> <td> Larry / Don </td> <td> lettuce </td> <td align="right"> 18 </td> <td align="right"> 1226 </td> </tr>
  <tr> <td> Larry / Don </td> <td> peas </td> <td align="right"> 1 </td> <td align="right"> 420 </td> </tr>
  <tr> <td> Larry / Don </td> <td> spinach </td> <td align="right"> 4 </td> <td align="right"> 418 </td> </tr>
  <tr> <td> Larry / Don </td> <td> tomatoes </td> <td align="right"> 5 </td> <td align="right"> 340 </td> </tr>
  <tr> <td> Leigh </td> <td> basil </td> <td align="right"> 4 </td> <td align="right"> 470 </td> </tr>
  <tr> <td> Leigh </td> <td> beets </td> <td align="right"> 4 </td> <td align="right"> 781 </td> </tr>
  <tr> <td> Leigh </td> <td> cabbage </td> <td align="right"> 3 </td> <td align="right"> 340 </td> </tr>
  <tr> <td> Leigh </td> <td> collards </td> <td align="right"> 2 </td> <td align="right"> 306 </td> </tr>
  <tr> <td> Leigh </td> <td> cucumbers </td> <td align="right"> 19 </td> <td align="right"> 1311 </td> </tr>
  <tr> <td> Leigh </td> <td> kale </td> <td align="right"> 32 </td> <td align="right"> 7253 </td> </tr>
  <tr> <td> Leigh </td> <td> leeks </td> <td align="right"> 4 </td> <td align="right"> 969 </td> </tr>
  <tr> <td> Leigh </td> <td> lettuce </td> <td align="right"> 7 </td> <td align="right"> 477 </td> </tr>
  <tr> <td> Leigh </td> <td> radishes </td> <td align="right"> 4 </td> <td align="right"> 327 </td> </tr>
  <tr> <td> Leigh </td> <td> squash </td> <td align="right"> 58 </td> <td align="right"> 4249 </td> </tr>
  <tr> <td> Leigh </td> <td> swiss chard </td> <td align="right"> 5 </td> <td align="right"> 431 </td> </tr>
  <tr> <td> Leigh </td> <td> tomatoes </td> <td align="right"> 4 </td> <td align="right"> 306 </td> </tr>
  <tr> <td> Leigh </td> <td> watermelon </td> <td align="right"> 14 </td> <td align="right"> 1907 </td> </tr>
  <tr> <td> Leigh </td> <td> zucchini </td> <td align="right"> 19 </td> <td align="right"> 1380 </td> </tr>
  <tr> <td> Leslee </td> <td> beets </td> <td align="right"> 62 </td> <td align="right"> 12201 </td> </tr>
  <tr> <td> Leslee </td> <td> brussel sprouts </td> <td align="right"> 2 </td> <td align="right"> 293 </td> </tr>
  <tr> <td> Leslee </td> <td> cilantro </td> <td align="right"> 0 </td> <td align="right"> 26 </td> </tr>
  <tr> <td> Leslee </td> <td> collards </td> <td align="right"> 60 </td> <td align="right"> 8240 </td> </tr>
  <tr> <td> Leslee </td> <td> kale </td> <td align="right"> 6 </td> <td align="right"> 1248 </td> </tr>
  <tr> <td> Leslee </td> <td> lettuce </td> <td align="right"> 4 </td> <td align="right"> 306 </td> </tr>
  <tr> <td> Leslee </td> <td> squash </td> <td align="right"> 20 </td> <td align="right"> 1416 </td> </tr>
  <tr> <td> Leslee </td> <td> tomatoes </td> <td align="right"> 8 </td> <td align="right"> 545 </td> </tr>
  <tr> <td> Madeline / Scott / Sue </td> <td> lettuce </td> <td align="right"> 2 </td> <td align="right"> 136 </td> </tr>
  <tr> <td> Madeline / Scott / Sue </td> <td> tomatoes </td> <td align="right"> 168 </td> <td align="right"> 11475 </td> </tr>
  <tr> <td> Melinda / Betsy / Bobbi </td> <td> broccoli </td> <td align="right"> 8 </td> <td align="right"> 1312 </td> </tr>
  <tr> <td> Melinda / Betsy / Bobbi </td> <td> cabbage </td> <td align="right"> 10 </td> <td align="right"> 1135 </td> </tr>
  <tr> <td> Melinda / Betsy / Bobbi </td> <td> collards </td> <td align="right"> 9 </td> <td align="right"> 1226 </td> </tr>
  <tr> <td> Melinda / Betsy / Bobbi </td> <td> kale </td> <td align="right"> 2 </td> <td align="right"> 454 </td> </tr>
  <tr> <td> Melinda / Betsy / Bobbi </td> <td> lettuce </td> <td align="right"> 4 </td> <td align="right"> 306 </td> </tr>
  <tr> <td> Melinda / Betsy / Bobbi </td> <td> tomatoes </td> <td align="right"> 2 </td> <td align="right"> 136 </td> </tr>
  <tr> <td> Melinda / Betsy / Bobbi </td> <td> zucchini </td> <td align="right"> 390 </td> <td align="right"> 28311 </td> </tr>
  <tr> <td> Michelle / Eli / Robin </td> <td> collards </td> <td align="right"> 2 </td> <td align="right"> 272 </td> </tr>
  <tr> <td> Michelle / Eli / Robin </td> <td> okra </td> <td align="right"> 5 </td> <td align="right"> 787 </td> </tr>
  <tr> <td> Michelle / Eli / Robin </td> <td> peppers </td> <td align="right"> 46 </td> <td align="right"> 4177 </td> </tr>
  <tr> <td> Michelle / Eli / Robin </td> <td> squash </td> <td align="right"> 10 </td> <td align="right"> 690 </td> </tr>
  <tr> <td> Rabbi / Rafaella </td> <td> corn </td> <td align="right"> 13 </td> <td align="right"> 5784 </td> </tr>
  <tr> <td> Rabbi / Rafaella </td> <td> swiss chard </td> <td align="right"> 2 </td> <td align="right"> 173 </td> </tr>
  <tr> <td> Rabbi / Rafaella </td> <td> tomatoes </td> <td align="right"> 14 </td> <td align="right"> 936 </td> </tr>
  <tr> <td> Rabbi / Rafaella </td> <td> zucchini </td> <td align="right"> 8 </td> <td align="right"> 581 </td> </tr>
  <tr> <td> Stephen </td> <td> beans </td> <td align="right"> 1 </td> <td align="right"> 141 </td> </tr>
  <tr> <td> Stephen </td> <td> squash </td> <td align="right"> 12 </td> <td align="right"> 872 </td> </tr>
  <tr> <td> Stephen </td> <td> tomatoes </td> <td align="right"> 232 </td> <td align="right"> 15799 </td> </tr>
   </table>

The full data for all years can be found [here](https://docs.google.com/spreadsheet/ccc?key=0AlYsW526rxsmdDhIVzM0VDYzRkdLOXlvcldfQkJtcnc&usp=sharing). 

## Comparison with prior years

We had good results for virtually everything we planted and very good yields for kale, zucchini and tomatoes. Results for most other crops were above average. 

![plot of chunk unnamed-chunk-5](assets/fig/unnamed-chunk-5-1.svg) 

Why else did things go so well this year? 

Like last year, we had more harvests from the garden than any prior year. Gardeners have harvested more than 450 times to date. Last year, we harvested around 400 times and no other prior year had more than 250 harvests. (This may be partly due to better reporting on harvests in the last few years.)

![plot of chunk unnamed-chunk-6](assets/fig/unnamed-chunk-6-1.svg) 

During the year, the most intense periods were at the end of June and July - gardeners harvested more than 250 pounds during each of these weeks. 

![plot of chunk unnamed-chunk-7](assets/fig/unnamed-chunk-7-1.svg) 

We harvested crops by far the most often on Sunday, and least often on Saturdays and Mondays. (Saturday visits may be after sundown or data entry errors on my part.)

![plot of chunk unnamed-chunk-8](assets/fig/unnamed-chunk-8-1.svg) 

When are various crops harvested? The charts below show the weekly harvests by crop for the past several years. Crops like beans and lettuce are harvested early, tomatoes and peppers later in the year and squash, collards and kale for longer periods. 

![plot of chunk unnamed-chunk-9](assets/fig/unnamed-chunk-9-1.svg) 

