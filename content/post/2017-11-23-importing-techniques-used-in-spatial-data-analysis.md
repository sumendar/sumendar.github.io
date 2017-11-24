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

**In this section, we are going to take a look at...**

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
## 'data.frame':	112 obs. of  22 variables:
##  $ time           : Factor w/ 112 levels "2017-11-23T11:50:50.090Z",..: 112 111 110 109 108 107 106 105 104 103 ...
##  $ latitude       : num  61.6 61.4 38.8 36.1 65.3 ...
##  $ longitude      : num  -146 -142 -123 -118 -163 ...
##  $ depth          : num  19.1 58.1 2.55 5.8 7.8 5.85 5.78 6.29 1.99 3.3 ...
##  $ mag            : num  3.1 2.5 0.9 1.21 2.9 1.84 0.18 0.79 1.31 1.19 ...
##  $ magType        : Factor w/ 5 levels "mb","mb_lg","md",..: 4 4 3 4 4 3 4 4 3 3 ...
##  $ nst            : int  NA NA 17 17 NA 27 14 21 13 15 ...
##  $ gap            : num  NA NA 73 101 NA 76 46 72 87 77 ...
##  $ dmin           : num  NA NA 0.000959 0.05882 NA ...
##  $ rms            : num  0.88 0.86 0.04 0.12 0.52 0.06 0.09 0.19 0.03 0.04 ...
##  $ net            : Factor w/ 9 levels "ak","ci","hv",..: 1 1 4 2 1 4 2 2 4 4 ...
##  $ id             : Factor w/ 112 levels "ak17388290","ak17388302",..: 22 23 83 46 21 82 45 44 81 80 ...
##  $ updated        : Factor w/ 112 levels "2017-11-23T12:51:02.351Z",..: 112 110 111 107 105 106 103 101 104 102 ...
##  $ place          : Factor w/ 101 levels "103km WNW of Talkeetna, Alaska",..: 58 17 87 67 24 15 4 54 98 20 ...
##  $ type           : Factor w/ 1 level "earthquake": 1 1 1 1 1 1 1 1 1 1 ...
##  $ horizontalError: num  NA NA 0.29 0.31 NA 0.33 0.19 0.41 0.37 0.31 ...
##  $ depthError     : num  0.5 2.2 0.53 0.59 0.2 0.99 0.57 0.74 0.6 0.45 ...
##  $ magError       : num  NA NA 0.05 0.185 NA 0.15 0.062 0.121 0.13 0.08 ...
##  $ magNst         : int  NA NA 4 19 NA 15 7 14 4 13 ...
##  $ status         : Factor w/ 2 levels "automatic","reviewed": 1 1 1 1 1 1 1 1 1 1 ...
##  $ locationSource : Factor w/ 9 levels "ak","ci","hv",..: 1 1 4 2 1 4 2 2 4 4 ...
##  $ magSource      : Factor w/ 9 levels "ak","ci","hv",..: 1 1 4 2 1 4 2 2 4 4 ...
```

##Downloading Open Data from FTP Sites 

**Often times, datasets are provided for free, but on FTP, websites and practitioners need to be able to access them. R is perfectly capable of downloading and importing data from FTP sites.**

**In this section, we are going to take a look at...**

* Understand the basics of downloading data in R
* Download the data with the download.file function
* Learn how to handle compressed formats


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

##Fixed-Width Format
**In this section, we are going to take a look at...**

* Creating a list of files in a folder
* Opening data compressed in gzip
* Opening data in fixed width format




```r
help(list.files)
```


```r
setwd("./NOAAFiles")
#Open the first file in the list
data <- read.fwf(gzfile(FileList[1],open="rt"),
                 header=F,
                 skip=1,
                 widths=c(6,1,5,2,8,4,4,108))
```

```
## Warning in readLines(file, n = skip): seek on a gzfile connection returned
## an internal error
```

```
## Warning in readLines(file, n = thisblock): seek on a gzfile connection
## returned an internal error
```

```
## Warning in readLines(file, n = thisblock): incomplete final line found on
## '339240-99999-2016.op.gz'
```


```r
str(data)
```

```
## 'data.frame':	325 obs. of  8 variables:
##  $ V1: int  339240 339240 339240 339240 339240 339240 339240 339240 339240 339240 ...
##  $ V2: logi  NA NA NA NA NA NA ...
##  $ V3: int  99999 99999 99999 99999 99999 99999 99999 99999 99999 99999 ...
##  $ V4: logi  NA NA NA NA NA NA ...
##  $ V5: int  20160101 20160102 20160103 20160104 20160105 20160106 20160107 20160108 20160109 20160110 ...
##  $ V6: logi  NA NA NA NA NA NA ...
##  $ V7: num  18.2 15.8 9.9 14 26.8 30.2 45.6 36.6 40.6 44.5 ...
##  $ V8: Factor w/ 324 levels "  5    40.7  5  1008.9  5  1007.7  5    5.5  5    5.1  5    7.8  999.9    49.6    37.2   0.30F 999.9  010000",..: 18 16 15 17 26 33 10 46 48 108 ...
```



```r
#Clean it from unwanted columns
data.clean <- data[,c("V1", "V3", "V5", "V7")]
```


```r
str(data.clean)
```

```
## 'data.frame':	325 obs. of  4 variables:
##  $ V1: int  339240 339240 339240 339240 339240 339240 339240 339240 339240 339240 ...
##  $ V3: int  99999 99999 99999 99999 99999 99999 99999 99999 99999 99999 ...
##  $ V5: int  20160101 20160102 20160103 20160104 20160105 20160106 20160107 20160108 20160109 20160110 ...
##  $ V7: num  18.2 15.8 9.9 14 26.8 30.2 45.6 36.6 40.6 44.5 ...
```



```r
#Change the names of the columns
names(data.clean) <- c("STN", "WBAN", "YEARMODA", "TEMP")
```





