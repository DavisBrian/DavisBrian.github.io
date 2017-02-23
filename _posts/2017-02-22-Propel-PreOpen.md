---
title: "\'Twas the night before the Open"
author: "Brian Davis"
date: "23 February, 2017"
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
 

|           Name|      Division       | Height |
|--------------:|:-------------------:|:------:|
| Mike Boessling| Masters Men (40-44) | 0' 6"  |
|   Hector Garza|   Individual Men    | 0' 6"  |
|  Jason Fennell| Masters Men (35-39) | 0' 5"  |
 
I assume they meant feet not inches when they were filling out their stats so I corrected them, although I'm pretty sure Jason is taller than 5 feet.
 
![plot of chunk height_plot](/figures/height_plot-1.png)
 
How many of you guys are actually 5’11” but thought it wouldn’t hurt anybody if you rounded up to 6’0″?  The large dip between 5'10" and 6'0" seems to indicate we have a couple guys with wishful thinking.
 
### Other Metrics
 
Originally I was going to do the above plots for each benchmark WOD.  Unfortunately, we either haven't done them recently or we didn't feel the desire to fill in our scores.
 

|Benchmark Stat | Count | Missing |
|:--------------|:-----:|:-------:|
|Deadlift       |  16   |   83    |
|Back Squat     |  15   |   84    |
|Clean And Jerk |  13   |   86    |
|Snatch         |  13   |   86    |
|Fran           |   8   |   91    |
|Grace          |   8   |   91    |
|Fight Gone Bad |   5   |   94    |
|Max Pullups    |   5   |   94    |
|Sprint 400m    |   5   |   94    |
|Filthy 50      |   4   |   95    |
|Helen          |   4   |   95    |
|Run 5k         |   4   |   95    |
 
### Final Thoughts
 
Well you made it to the end!  Hopefully I'll get the team members for each of our internal teams and I can break down the scores of each workout by team.  Otherwise I'll just summarize for the gym overall.
