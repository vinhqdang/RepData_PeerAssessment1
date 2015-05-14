# Reproducible Research: Peer Assessment 1


## Loading and preprocessing the data

```r
data = read.csv ("activity.csv")
totalSteps<-aggregate(steps~date,data=data,sum,na.rm=TRUE)
```


## What is mean total number of steps taken per day?

```r
hist (totalSteps$steps, main = "Histogram of number of steps", xlab = "Number of steps")
```

![](PA1_template_files/figure-html/unnamed-chunk-2-1.png) 

```r
mean (totalSteps$steps)
```

```
## [1] 10766.19
```

```r
median (totalSteps$steps)
```

```
## [1] 10765
```


## What is the average daily activity pattern?

```r
stepsInterval<-aggregate(steps~interval,data=data,mean,na.rm=TRUE)
plot(steps~interval,data=stepsInterval,type="l")
```

![](PA1_template_files/figure-html/unnamed-chunk-3-1.png) 

## Which interval contains maximum of steps


```r
stepsInterval[which.max(stepsInterval$steps),]$interval
```

```
## [1] 835
```


## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
