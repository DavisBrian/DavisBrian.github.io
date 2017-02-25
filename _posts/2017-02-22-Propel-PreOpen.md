---
title: "\'Twas the night before the Open"
author: "Brian Davis"
date: "25 February, 2017"
published: true
status: publish
draft: false
output: html_document
---
 

 
How does a data scientist prepare for the [Crossfit
Open](https://games.crossfit.com/)?  You scrape the games site and analyze it of
course.
 
Since [our gym](http://crossfitpropel.com/) is having our own head-head
throw-down for each Open workout I figured I'd take a look at our Open
participation stats.  Here is a quick look at how the 99
athletes we have registered for the Crossfit Open breakdown. 
 
 
### Age
 
![plot of chunk age](/figures/age-1.png)
 
As gym we have every division **except** Teenage (16-17) represented.  We have
strong millennial representation, but we also have a large 40+ crowd too. 
Now "Get off my lawn!"
 
### Height
 
The first thing I noticed when I looked at the height of our participants is a couple people seemed to have filled out their profile a bit wrong.
 
<table>
<col width="200">
<col width="200">
 <thead>
  <tr>
   <th style="text-align:right;"> Name </th>
   <th style="text-align:center;"> Division </th>
   <th style="text-align:center;"> Height </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:right;"> Mike Boessling </td>
   <td style="text-align:center;"> Masters Men (40-44) </td>
   <td style="text-align:center;"> 0' 6&quot; </td>
  </tr>
  <tr>
   <td style="text-align:right;"> Hector Garza </td>
   <td style="text-align:center;"> Individual Men </td>
   <td style="text-align:center;"> 0' 6&quot; </td>
  </tr>
  <tr>
   <td style="text-align:right;"> Jason Fennell </td>
   <td style="text-align:center;"> Masters Men (35-39) </td>
   <td style="text-align:center;"> 0' 5&quot; </td>
  </tr>
</tbody>
</table>
 
 
I assume they meant feet not inches when they were filling out their stats so I corrected them, although I'm pretty sure Jason is taller than 5 feet.
 
![plot of chunk height_plot](/figures/height_plot-1.png)
 
How many of you guys are actually 5’11” but thought it wouldn’t hurt anybody if you rounded up to 6’0″?  The large dip between 5'10" and 6'0" seems to indicate we have a couple guys with wishful thinking.
 
### Other Metrics
 
Originally I was going to do the above plots for each benchmark WOD.  Unfortunately, we either haven't done them recently or we didn't feel the desire to fill in our scores.
 
<table>
<col width="150">
<col width="100">
 <thead>
  <tr>
   <th style="text-align:left;"> Benchmark Stat </th>
   <th style="text-align:center;"> Count </th>
   <th style="text-align:center;"> Missing </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> Deadlift </td>
   <td style="text-align:center;"> 16 </td>
   <td style="text-align:center;"> 83 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Back Squat </td>
   <td style="text-align:center;"> 15 </td>
   <td style="text-align:center;"> 84 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Clean And Jerk </td>
   <td style="text-align:center;"> 13 </td>
   <td style="text-align:center;"> 86 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Snatch </td>
   <td style="text-align:center;"> 13 </td>
   <td style="text-align:center;"> 86 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Fran </td>
   <td style="text-align:center;"> 8 </td>
   <td style="text-align:center;"> 91 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Grace </td>
   <td style="text-align:center;"> 8 </td>
   <td style="text-align:center;"> 91 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Fight Gone Bad </td>
   <td style="text-align:center;"> 5 </td>
   <td style="text-align:center;"> 94 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Max Pullups </td>
   <td style="text-align:center;"> 5 </td>
   <td style="text-align:center;"> 94 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Sprint 400m </td>
   <td style="text-align:center;"> 5 </td>
   <td style="text-align:center;"> 94 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Filthy 50 </td>
   <td style="text-align:center;"> 4 </td>
   <td style="text-align:center;"> 95 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Helen </td>
   <td style="text-align:center;"> 4 </td>
   <td style="text-align:center;"> 95 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Run 5k </td>
   <td style="text-align:center;"> 4 </td>
   <td style="text-align:center;"> 95 </td>
  </tr>
</tbody>
</table>
 
### Final Thoughts
 
Well you made it to the end!  Hopefully I'll get the team members for each of our internal teams and I can break down the scores of each workout by team.  Otherwise I'll just summarize for the gym overall.
