
# Ass Number 1


## Set up steps

### Set up the values for the simulation

```r
set.seed(667)
sims <- 1000
n <- 40
lambda <- 0.2
```

### Create a Matrix


```r
## create a matrix of a 1000 rows of 40 random exponential values
sim <- matrix(rexp(sims * n, rate = lambda), sims)
```


## 1. This is question number 1

### Take the mean for each row

```r
row_means<-rowMeans(sim)
mean(row_means)
```

```
## [1] 5.025859
```

### Theoretical mean of the sample:


```r
1/lambda
```

```
## [1] 5
```


## 2. This is question number 2

### take the sd of each rowMeans

```r
(1/lambda)^2/n
```

```
## [1] 0.625
```

### Theoretical sd

```r
var(row_means)
```

```
## [1] 0.6286297
```


## 3. This is question number 3

### This histogram visually shows how the ** resembles the **.


```r
h<-hist(means, breaks=50, density=20, col="gray", xlab="Accuracy", main="Overall")
    xfit<-seq(min(means),max(means),length=40)
    yfit<-dnorm(xfit,mean=mean(means),sd=sd(means))
    yfit <- yfit*diff(h$mids[1:2])*length(means)
    lines(xfit, yfit, col="blue", lwd=2)
```

![plot of chunk unnamed-chunk-7](figure/unnamed-chunk-7-1.png)
