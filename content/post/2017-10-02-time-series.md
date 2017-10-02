---
title: Time Series
author: Galen
date: '2017-10-02'
slug: time-series
categories:
  - R
tags:
  - plot
---


library(sqldf)
library(ggplot2)
library(Lahman)



#Extracting data


query<-"select yearID, HR 
from Batting 
where playerID='ruthba01'"

result<-sqldf(query)



#Visualizing data


ggplot()+
  #geom_point(data=result,aes(x=yearID,y=HR), color='red')+
  geom_line(data=result,aes(x=yearID,y=HR), color='green')+
  ggtitle("Babe Ruth's Homerun Totals During Career")+
  xlab("Year")+
  ylab("Homeruns")

