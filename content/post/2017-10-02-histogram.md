---
title: Histogram
author: Galen
date: '2017-10-02'
slug: histogram
categories:
  - R
tags:
  - plot
---



library(sqldf)
library(ggplot2)
library(Lahman)



#Extracting Data

query<-"Select weight from Master"
result<-sqldf(query)



#Visualizing Data

ggplot()+
  geom_histogram(data=result,aes(x=weight), color='white', fill='blue', bins=60)+
  ggtitle("Body Weight Distribution for Baseball players")
