# COVID-19: Data Animation in R (and RStudio)

<p align="center">
  <img src="assets/A3_COV19_Rviz3.gif" alt="animated"/>
</p>


## Ready, set, gif! (Background)

The bar chart race, a type of bar chart but with a little more pizazz, has gone viral across social media platforms. But despite its obvious popularity, can the humble bar chart really give useful insight into the spread of the COVID-19 pandemic? I think it can.

The success of a bar chart lies in its simplicity. When it comes to comparing the values of things, especially categories of things, the bar graph is one of the most commonly used visualisations, and for a good reason. It’s intuitive, easy to read and interpret even for those without a background in data. But this simplicity comes at a cost; a typical bar chart will
convey at most two dimensions of data, and is less useful for showing how this data changes over time. Enter the bar chart race.

An animated bar chart, or a <em>bar chart race</em>, is an interesting way to show how categorical data changes over time. A bar chart race is to a static bar chart as a movie is to an image, it is simply a stacked collection of images (or frames) stitched together in the correct order and played sequentially. And when used to visualise the spread of COVID-19, it can yield some interesting results.

The gif above compares confirmed COVID-19 cases by country over the period January 22<sup>nd</sup> to March 31<sup>st</sup>. At a glance, it's easy to take away the following:


- The number of confirmed COVID-19 cases in China seems to grow exponentially1 through January and February far exceeding other countries around the world before being replaced by Italy and then the US (the current epicenter of the disease as of March 31st).

- The number of recovered cases in China increases steadily, picking up pace towards the end of February. At the same time, the number of new confirmed cases seem to slow. By the first week of March, the majority of patient outcomes were reported as recovered. (While all countries have a fair share of recovered outcomes, by the end of March China is the only country in which the majority of cases are recovered.)

- For all countries, the number of COVID-19 cases that result in death (black bar) are a small percentage of total cases, but Italy and Spain have a higher percentage of reported deaths when compared to all other countries on the list.

- By the end of March, it’s clear that Europe has the highest number of COVID-19 cases, with 6 nations taking top spots in the ranking. By contrast, at the end of January, 7 of the top 10 ranked countries were Asian nations (Germany the single European nation).

Disclaimer: TALK ABOUT HOW A GOOD VISUALISATION SHOULD GIVE YOU ALL THE INFORMATION YOU NEED WITHIN A COUPLE SECONDS. AND A STATIC CAN ACHIVE THE ABOVE. GET HEATMAP TO DEMONSTRATE.

LIKE THIS:

Note
In preparing the gif, I have tried to adhere to as many good principles of design as possible. A notable exception is the x-axis. While there is a title, there are no tick marks and no grid lines. I did this because I wanted to include the 2nd part (confirmed cases per 100k population) in a single gif, and this part works on a different scale to the 1st. It has been correctly scaled, but it’s tricky to label. However, I do feel that providing labels for the confirmed (red) bar somewhat softens the need for gridlines, as the value does not have to be read off, but of course it would have been more ideal to include them. And while the green and black bars are meant only for getting a visual estimate, gridlines would have allowed for a more precise estimate.
Resources
https://towardsdatascience.com/channel-your-creativity-interactive-and-animated-graphics-in-r-with-covid-19-data-5f7bede4b29f
https://towardsdatascience.com/create-animated-bar-charts-using-r-31d09e5841da
https://towardsdatascience.com/https-towardsdatascience-com-everything-you-need-to-know-about-animated-bar-charts-be033f398619
https://medium.com/@korkmazarda1/creating-an-animated-bar-plot-in-r-de9200f57506

## Installation

ALSO DO THIS HERE.

```r

## data frame manipulation
if(!require(tidyverse)) {install.packages("tidyverse"); library(tidyverse)}
if(!require(lubridate)) {install.packages("lubridate"); library(lubridate)}

### animated plots
if(!require(ggplot2)) {install.packages("ggplot2"); library(ggplot2)}
if(!require(gganimate)) {install.packages("gganimate"); library(gganimate)}
if(!require(transformr)) {install.packages("transformr"); library(transformr)}
if(!require(gifski)) {install.packages("gifski"); library(gifski)}
if(!require(av)) {install.packages("av"); library(av)}

### labelling plots
if(!require(directlabels)) {install.packages("directlabels"); library(directlabels)}
if(!require(ggrepel)) {install.packages("ggrepel"); library(ggrepel)}
  
```