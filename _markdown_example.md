---
title: "R Markdown Demo"
author: Simon Schölzel    
date: "27 September, 2021"     
output:              
  html_document:     
    toc: true        
    toc_float: true  
    toc_depth: 2
    keep_md: true
---

# Markdown Examples

<iframe src="https://player.vimeo.com/video/178485416?color=428bca" width="480" height="300" frameborder="0" allow="autoplay; fullscreen" allowfullscreen>

</iframe>

## The Fibnoacci Series

![](http://t1.gstatic.com/licensed-image?q=tbn:ANd9GcQ-i8vSXstr4BR4br6yUDM6o4esu6TFZdLVsqjfBWIT8vaXdoCSDi3bw93Iir4l)

**Wikipedia extract:** Fibonacci numbers are named after Italian mathematician *Leonardo of Pisa*, later known as Fibonacci. In his 1202 book Liber Abaci, Fibonacci introduced the sequence to Western European mathematics,[5] although the sequence had been described earlier in Indian mathematics, as early as 200 BC in work by Pingala on enumerating possible patterns of Sanskrit poetry formed from syllables of two lengths. [Source](https://en.wikipedia.org/wiki/Fibonacci_number)


```r
fib <- function(n) {
  x <-  numeric(n)
  x[1:2] <- c(1,1)
  for(i in 3:n) {
    x[i] = x[i-1] + x[i-2]
  }
  return(x)
}

Sys.sleep(5)

fib(10)
```

```
##  [1]  1  1  2  3  5  8 13 21 34 55
```

We can even run in-line, so-called inline expressions: 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, 233, 377, 610.

Return the first 100 elements of the series:


```
##   [1] 1.000000e+00 1.000000e+00 2.000000e+00 3.000000e+00 5.000000e+00
##   [6] 8.000000e+00 1.300000e+01 2.100000e+01 3.400000e+01 5.500000e+01
##  [11] 8.900000e+01 1.440000e+02 2.330000e+02 3.770000e+02 6.100000e+02
##  [16] 9.870000e+02 1.597000e+03 2.584000e+03 4.181000e+03 6.765000e+03
##  [21] 1.094600e+04 1.771100e+04 2.865700e+04 4.636800e+04 7.502500e+04
##  [26] 1.213930e+05 1.964180e+05 3.178110e+05 5.142290e+05 8.320400e+05
##  [31] 1.346269e+06 2.178309e+06 3.524578e+06 5.702887e+06 9.227465e+06
##  [36] 1.493035e+07 2.415782e+07 3.908817e+07 6.324599e+07 1.023342e+08
##  [41] 1.655801e+08 2.679143e+08 4.334944e+08 7.014087e+08 1.134903e+09
##  [46] 1.836312e+09 2.971215e+09 4.807527e+09 7.778742e+09 1.258627e+10
##  [51] 2.036501e+10 3.295128e+10 5.331629e+10 8.626757e+10 1.395839e+11
##  [56] 2.258514e+11 3.654353e+11 5.912867e+11 9.567220e+11 1.548009e+12
##  [61] 2.504731e+12 4.052740e+12 6.557470e+12 1.061021e+13 1.716768e+13
##  [66] 2.777789e+13 4.494557e+13 7.272346e+13 1.176690e+14 1.903925e+14
##  [71] 3.080615e+14 4.984540e+14 8.065155e+14 1.304970e+15 2.111485e+15
##  [76] 3.416455e+15 5.527940e+15 8.944394e+15 1.447233e+16 2.341673e+16
##  [81] 3.788906e+16 6.130579e+16 9.919485e+16 1.605006e+17 2.596955e+17
##  [86] 4.201961e+17 6.798916e+17 1.100088e+18 1.779979e+18 2.880067e+18
##  [91] 4.660047e+18 7.540114e+18 1.220016e+19 1.974027e+19 3.194043e+19
##  [96] 5.168071e+19 8.362114e+19 1.353019e+20 2.189230e+20 3.542248e+20
```

## The famous `mtcars` dataset

The `mtcars` data was extracted from the 1974 *Motor Trend* US magazine, and comprises fuel consumption and 10 aspects of automobile design and performance for 32 automobiles (1973--74 models).

## Solving quadratic equations

Take a quadratic equation[^1] of the form:

[^1]: See [Wikipedia](https://en.wikipedia.org/wiki/Quadratic_equation)

$$ x^2 + p * x + q = 0 $$ where $p$ and $q$ are the function coefficients.

This type of equation can be solved using the *p-q-formula*:

$$x_{1/2} = -\frac{p}{2}\pm \sqrt{(\frac{p}{2})^2-q}$$
