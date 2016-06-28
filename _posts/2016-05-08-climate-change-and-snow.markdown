---
layout: post
title: Climate Change and Snow - The Real Story
date:   2016-05-08
categories: politics
author: Adam Bodie
image: inhofe.jpg
alt: Jim Inhofe
intro: "Climate change is real.  97% of all scientists believe the Earth is getting abnormally hotter than usual because of greenhouse gases polluting the Earth.  But there are some people who believe it's a hoax.  Most likely it's to protect their greenhouse gas producing fuels and chemicals.  Others are religious nuts who hate science as it counters religion.  They'll find any excuse to discredit global warming and climate change as to protect their profit, and gain the support of those who disapprove man-made climate change, mostly members of the Republican Party."
---
<style>
#inhofe {
	float: right;
	padding: 20px;
}

.axis path,
.axis line {
  fill: none;
  stroke: #000;
  shape-rendering: crispEdges;
}


.pdxLine {
  fill: none;
  stroke: steelblue;
  stroke-width: 2px;
}

.pdxLine:hover {
	stroke-width: 4px;
}

.nycLine {
	fill: none;
	stroke: green;
	stroke-width: 2px;
}

.nycLine:hover {
	stroke-width: 4px;
}
svg {
	display: block;
	margin-left: auto;
	margin-right: auto;
	background-color: white;
	font: 10px sans-serif;
}

.key {
    padding: 10px;
    border-radius: 50%;
    display: inline-block;
}


</style>
<div class="article">
<p> {{ page.intro }}</p>
<div class="blog-pic">
		<img src="/img/inhofe.jpg" data-toggle="tooltip" title="Jim Inhofe" class="image block img-responsive" id="inhofe">
		<h4>In Washington D.C., it snows virtually every winter.  Doesn't prove a thing.</h4>
</div>
		<p>Enter Jim Inhofe, the senior Republican Senator of Oklahoma and for some reason, the chair of the Senate Committee on Environment and Public Works.  Senator Inhofe has long been a denier of climate change, and a cold winter day on February 26, 2015, Senator Inhofe blasted global warming as a hoax.  His reasoning: It was snowing outside.  He even brought in a snowball to a Congressional Hearing to back up his claim, because according to him, how can we have global warming when it's so cold outside.  So despite average temperatures trending upward since the 1970s, does Inhofe's snow theory hold up?</p>
		
		<p>Anyone with half a brain knows it doesn't get hot in our Winter. Since the Earth's rotated at 24.5 degrees, we have different seasons and when our axis is away from the sun, it gets colder as opposed to the axis being towards the sun, when it gets hotter.  Yet Senator Inhofe thinks Global Warming only makes things hotter.  A native Portlander, I have seen many winters come and go in Portland with little to no snow, despite a decently cold temperature.  When I was younger, I saw a lot more snowy days in Portland.  Now, we've had just a few years with any major snowstorms.  As you can see from the graph below, I've compared snowfall levels of both Portland and New York City (where it is more likely to snow), and looking at the data, doesn't prove that Global Warming doesn't exist.</p>

	<p>As the data below shows, there is no reason to believe that snow has anything to do with global warming.  In fact, Portland shows a drop in snowfall over the years.  The snowstorm of 2008-2009 was a freak snowstorm for us here in Portland; we had not seen that much snow in that year.  But as the data shows, we in Portland saw little to no snow during the rest of that decade.  It's true that Portland doesn't represent the United States as a whole, but by Inhofe's thinking, there would be little to no variation in the yearly data.  Looking at the data for New York City, there's no variation in snow levels, varying year to year.  But this has nothing to do with temperature.  On the flipside is Phoenix, where it rarely, if ever, snows.  Senator Inhofe's snow argument wouldn't get much muster in Phoenix.</p>
	<p>I can't tell you where Senator Inhofe gets his ideas from.  But as someone who gets plenty of campaign money from the oil and gas industries, it would come as no shock if his opinions are being paid for.  After all, these companies are polluting the air with little regard to the environment.  But while that factor will always be there, it's Inhofe's religious stance that may be a greater cause of concern.  In 2012, Inhofe cited the Bible as irrefutable proof that climate change isn't man-made.  His quote: <em>"[T]he Genesis 8:22 that I use in there is that 'as long as the earth remains there will be seed time and harvest, cold and heat, winter and summer, day and night.' My point is, God's still up there. The arrogance of people to think that we, human beings, would be able to change what He is doing in the climate is to me outrageous."</em> But really, why would God choose 2014 to become the hottest average temperature on the existence of Earth since they started measuring, and then break that record the following year.  Some things are easier to identify and prove than with God's will.</p>
	<h3 id="title">Snowfall from 1871-2009 in New York City and Portland</h3>
	<div id="info" style="width: 1100px;">
   	<div id="keys">
      	<p>
            <span class="key" style="background: steelblue;"></span>
            <span class="key-text">Portland</span>
         </p>
         <p>
         	<span class="key" style="background: green;"></span>
         	<span class="key-text">New York</span>
         </p>
      </div>	
	<script src="//d3js.org/d3.v3.min.js"></script>
	<script>

var margin = {top: 20, right: 20, bottom: 30, left: 50},
    width = 960 - margin.left - margin.right,
    height = 500 - margin.top - margin.bottom;

var formatDate = d3.time.format("%Y");

var x = d3.time.scale()
    .range([0, width]);

var y = d3.scale.linear()
    .range([height, 0]);

var xAxis = d3.svg.axis()
    .scale(x)
    .orient("bottom");

var yAxis = d3.svg.axis()
    .scale(y)
    .orient("left");

var pdxLine = d3.svg.line()
    .x(function(d) { return x(d.date); })
    .y(function(d) { return y(d.pdx); });
    
var nycLine = d3.svg.line()
    .x(function(d) { return x(d.date); })
    .y(function(d) { return y(d.nyc); });    
				
var svg = d3.select("body")
	 .append("svg")
    .attr("width", width + margin.left + margin.right)
    .attr("height", height + margin.top + margin.bottom)
  	 .append("g")
    .attr("transform", "translate(" + margin.left + "," + margin.top + ")");


d3.tsv("/data/data.tsv", type, function(error, data) {
  if (error) throw error;
  
  x.domain(d3.extent(data, function(d) { return d.date; }));
  y.domain(d3.extent(data, function(d) { return d.nyc; }));

  svg.append("g")
      .attr("class", "x axis")
      .attr("transform", "translate(0," + height + ")")
      .call(xAxis);

  svg.append("g")
      .attr("class", "y axis")
      .call(yAxis)
    .append("text")
      .attr("transform", "rotate(-90)")
      .attr("y", 10)
      .attr("dy", ".71em")
      .style("text-anchor", "end")
      .text("Snowfall (inches)");
  		
  svg.append("path")
      .datum(data)
      .attr("class", "pdxLine")
      .attr("d", pdxLine);
 
 	svg.append("path")
 		.datum(data)
 		.attr("class", "nycLine")
 		.attr("d", nycLine);
 
});

function type(d) {
  d.date = formatDate.parse(d.date);
  d.pdx = +d.pdx;
  d.nyc = +d.nyc;
  return d;
}

</script>
	
</div>