# COVID-19: Data Animation in R (and RStudio)

INTRO HERE.

<p align="center">
  <img src="assets/A3_COV19_Rviz3.gif" alt="animated"/>
</p>


## Background

The bar chart race, a type of bar chart but with a little more pizazz, has gone viral across social media platforms. But despite its obvious popularity, can the humble bar chart really give useful insight into the spread of the COVID-19 pandemic? I think it can.

The success of a bar chart lies in its simplicity. When it comes to comparing the values of things, especially categories of things, the bar graph is one of the most commonly used visualisations, and for a good reason. It’s intuitive, easy to read and interpret even for those without a background in data. But this simplicity comes at a cost; a typical bar chart will
convey at most two dimensions of data, and is less useful for showing how this data changes over time. Enter the bar chart race.

An animated bar chart, or a bar chart race, is an interesting way to show how categorical data changes over time. A bar chart race is to a static bar chart as a movie is to an image, it is simply a stacked collection of images (or frames) stitched together in the correct order and played sequentially. And when used to visualise the spread of COVID-19, it can yield some interesting results.

The gif above compares confirmed COVID-19 cases by country over the period January 22nd to March 31st, in two parts: first by the total confirmed cases per country, and second, by confirmed cases adjusted for the relative size of the population of each country (in this case, per 100,000). The latter, which is generally the gold standard for comparing country level statistics like crime, provides a new perspective - for example, the US may have the largest number of confirmed cases in the world, but when taking into account the comparatively large population of the US, it falls somewhere in the middle of its peers.
Total confirmed cases

TIP: Useful for tracking the spread of COVID-19 around the world, but not so useful in making comparisons between countries.

The number of confirmed COVID-19 cases in China seems to grow exponentially1 through January and February far exceeding other countries around the world before being replaced by Italy and then the US (the current epicenter of the disease as of March 31st).

The number of recovered cases in China increases steadily, picking up pace towards the end of February. At the same time, the number of new confirmed cases seem to slow. By the first week of March, the majority of patient outcomes were reported as recovered. (While all countries have a fair share of recovered outcomes, by the end of March China is the only country in which the majority of cases are recovered.)

For all countries, the number of COVID-19 cases that result in death (black bar) are a small percentage of total cases, but Italy and Spain have a higher percentage of reported deaths when compared to all other countries on the list.

By the end of March, it’s clear that Europe has the highest number of COVID-19 cases, with 6 nations taking top spots in the ranking. By contrast, at the end of January, 7 of the top 10 ranked countries were Asian nations (Germany the single European nation).

## Installation

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