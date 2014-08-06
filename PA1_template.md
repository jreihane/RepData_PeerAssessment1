
```r
setwd("G:\\Projects\\R\\Reproducible\\RepData_PeerAssessment1")
```


# Reproducible Research: Peer Assessment 1


## Loading and preprocessing the data

```r
dataFile <- read.csv("activity2.csv")
dataFile$date <- as.Date(dataFile$date, format = "%d/%m/%Y")
```


## What is mean total number of steps taken per day?

```r
d2 <- with(dataFile, split(steps,date))
s1 <- lapply(d2,sum, na.rm = T)
s2 <- unsplit(value = s1,f = dataFile$date)

hist(s2,xlab="per day")
(meann <- lapply(d2,mean,na.rm=TRUE))
(mediann <- lapply(d2,median,na.rm=TRUE))

```

![plot of chunk mm](figure/mm.png) 

```r
meann <- lapply(d2, mean, na.rm = TRUE)
mediann <- lapply(d2, mean, na.rm = TRUE)

c1 <- matrix(c(meann, mediann), dimnames = list(c(), c("mean", "median")), ncol = 2)
```

mean and median of the steps in each day is:

```r
(c1)
```

```
##       mean   median
##  [1,] NaN    NaN   
##  [2,] NaN    NaN   
##  [3,] 0.4375 0.4375
##  [4,] 36.81  36.81 
##  [5,] 39.42  39.42 
##  [6,] 36.7   36.7  
##  [7,] 42.07  42.07 
##  [8,] NaN    NaN   
##  [9,] 46.16  46.16 
## [10,] 36.25  36.25 
## [11,] 53.54  53.54 
## [12,] 28.94  28.94 
## [13,] 38.25  38.25 
## [14,] 44.73  44.73 
## [15,] NaN    NaN   
## [16,] 11.18  11.18 
## [17,] 44.48  44.48 
## [18,] NaN    NaN   
## [19,] 34.38  34.38 
## [20,] NaN    NaN   
## [21,] 35.78  35.78 
## [22,] 43.78  43.78 
## [23,] 60.35  60.35 
## [24,] 37.38  37.38
```


## What is the average daily activity pattern?



## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
