---
title: Importing Techniques Used in Spatial Data Analysis
author: sumendar
date: '2017-11-23'
slug: importing-techniques-used-in-spatial-data-analysis
categories: []
tags: []
output: 
  html_document: 
    keep_md: yes
    toc: yes
---

**In this post we are going to take a look at various data importing techniques used for spatial data analysis**

## Importing Data from Tables (read.table)

* Opening data
* Importing csv files
* Checking the data structure for consistency

**Accessing and importing open access environmental data is a crucial skill for data scientists. This section teaches you how to download data from the Web, import it in R and check it for consistency.**

* Download open-access data from the USGS website
* Import it in R using read.table
* Check its structure to start exploring the data





```r
#Set the URL with the CSV Files
URL <- "http://earthquake.usgs.gov/earthquakes/feed/v1.0/summary/all_day.csv"
```


```r
#Load the CSV File
Data <- read.table(file=URL, 
                   sep=",", 
                   header=TRUE, 
                   na.string="")
```


```r
#Help function
help(read.table)
```


```r
#Examining the data
str(Data)
```

```
## 'data.frame':	115 obs. of  22 variables:
##  $ time           : Factor w/ 115 levels "2017-11-23T09:48:07.728Z",..: 115 114 113 112 111 110 109 108 107 106 ...
##  $ latitude       : num  38.8 38.8 38.8 37.5 46.7 ...
##  $ longitude      : num  -123 -123 -123 -119 -121 ...
##  $ depth          : num  2.01 1.57 1.57 4.36 12.34 ...
##  $ mag            : num  0.93 0.97 2.82 1.25 1.42 1.38 1.6 1.47 1.18 1.1 ...
##  $ magType        : Factor w/ 5 levels "mb","mb_lg","md",..: 3 3 3 3 3 3 4 3 4 4 ...
##  $ nst            : int  12 12 41 18 7 24 NA 10 47 NA ...
##  $ gap            : num  85 114 59 149 304 88 NA 190 119 NA ...
##  $ dmin           : num  0.00347 0.00293 0.00198 0.04735 0.206 ...
##  $ rms            : num  0.02 0.04 0.05 0.02 0.08 0.03 0.51 0.08 0.23 0.71 ...
##  $ net            : Factor w/ 9 levels "ak","ci","hv",..: 4 4 4 4 9 4 1 4 2 1 ...
##  $ id             : Factor w/ 115 levels "ak17388233","ak17388250",..: 83 82 81 80 115 79 25 78 49 24 ...
##  $ updated        : Factor w/ 115 levels "2017-11-23T10:00:52.149Z",..: 115 114 113 112 110 111 106 108 105 104 ...
##  $ place          : Factor w/ 105 levels "103km WNW of Talkeetna, Alaska",..: 103 104 103 23 30 87 1 31 21 2 ...
##  $ type           : Factor w/ 1 level "earthquake": 1 1 1 1 1 1 1 1 1 1 ...
##  $ horizontalError: num  0.29 0.35 0.14 0.3 5.63 0.35 NA 0.83 0.34 NA ...
##  $ depthError     : num  0.71 0.35 0.23 0.81 5.85 0.45 0.3 2 1.2 0.3 ...
##  $ magError       : num  0.05 0.07 0.13 0.09 0.3 0.15 NA 0.26 0.132 NA ...
##  $ magNst         : int  2 4 30 15 4 19 NA 8 26 NA ...
##  $ status         : Factor w/ 2 levels "automatic","reviewed": 1 1 1 1 1 1 1 1 1 1 ...
##  $ locationSource : Factor w/ 9 levels "ak","ci","hv",..: 4 4 4 4 9 4 1 4 2 1 ...
##  $ magSource      : Factor w/ 9 levels "ak","ci","hv",..: 4 4 4 4 9 4 1 4 2 1 ...
```

##Downloading Open Data from FTP Sites 

**Often times, datasets are provided for free, but on FTP, websites and practitioners need to be able to access them. R is perfectly capable of downloading and importing data from FTP sites.**

Understand the basics of downloading data in R
Download the data with the download.file function
Learn how to handle compressed formats


```r
#Load required packages
library(RCurl)
```

```
## Loading required package: bitops
```

```r
library(XML)
```



```r
#Create a list with all the files on the FTP site
list <- getURL("ftp://ftp.ncdc.noaa.gov/pub/data/gsod/2016/", 
               dirlistonly = TRUE) 
```


```r
#Clean the list 
FileList <- strsplit(list, split="\r\n")
```


```r
#Create a new directory where to download these files
DIR <- paste(getwd(),"/NOAAFiles",sep="")
dir.create(DIR)
```

```
## Warning in dir.create(DIR): 'E:\Projects\sumendar.github.io\content\post
## \NOAAFiles' already exists
```



```r
#Loop to download the files
for(FileName in unlist(FileList)){
  URL <- paste0("ftp://ftp.ncdc.noaa.gov/pub/data/gsod/2016/",FileName)
  download.file(URL, destfile=paste0(DIR,"/",FileName), method="auto", 
                mode="wb")
}
```


```r
#A more elegant way
DownloadFile <- function(x){
  URL <- paste0("ftp://ftp.ncdc.noaa.gov/pub/data/gsod/2016/",x)
  download.file(URL, destfile=paste0(DIR,"/",x), method="auto", mode="wb")
}
lapply(unlist(FileList)[1:5], DownloadFile)
```


```r
#Dowload a compressed file
URL <- "ftp://ftp.ncdc.noaa.gov/pub/data/gsod/2015/gsod_2015.tar"
download.file(URL, destfile=paste0(DIR,"/gsod_2015.tar"),
              method="auto",mode="wb")

untar(paste0(getwd(),"/NOAAFiles/","gsod_2015.tar"), 
      exdir=paste0(getwd(),"/NOAAFiles"))
```



```r
help(unzip)


#For more information on the full experiment please visit:
#http://r-video-tutorial.blogspot.ch/2014/12/accessing-cleaning-and-plotting-noaa.html
```


