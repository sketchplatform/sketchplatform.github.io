---
layout: post
title: HR Dataset
---

Introduction) Human Resource Analytics
--------------------------------------

**Questions:**

-   So why do our best and most experienced employees leave prematurely?
-   How can we normalize effort levels based on employee salary?
-   Would a better salary & work environment improve effort/satisfication levels?
-   Which sales industry performs better? What would happen if you were to introduce competition?
-   Can you anaylze the decision or preferences made by your empolyees?

**Variables (That I make for clarfication):**

-   `satisfaction_level`: Satisfaction level from (.09 - 1) probably filled in by employee.

-   `last_evaluation`: Last\_evaluation (performance) level from (.36 - 1) probably filled in by the employee's manager.

-   `number_project`: Number of projects that the employee has worked on.

-   `average_monthly_hours`: The average number of hours an employee worked in a month.

-   `time_spend_company`: Could this be the number of years an employee worked for this company?

-   `Work_accident`: Whether an employee has had an accident or not (0 = no, 1 = yes).

-   `left`: Whether an employee has left or not (0 = no, 1 = yes).

-   `promoted_last_5years`: Whether an employee has a promotion or not (0 = no, 1 = yes).

-   `sales`: The different department sectors of this company.

-   `salary`: Three-level salary ranging from (`low`, `medium`, `high`).

Descripitive Analytics) Exploring the Data
------------------------------------------

First I want to import and explore the Human Resource Dataset

``` r
HRanalytics <- read.csv("HR_analytics.csv", header = TRUE)
```

Always check for null values. In this example, we have specifically choosen a clean dataset (so there are no null values). However, not all dataset are clean and NA values can be a problem. When dealing with NA values you are left with 3 options keep it, remove it, or replace it. There are several techniques for handling null values, but we will cover them later down the line.

``` r
sum(is.na(HRanalytics))
```

Let's start making comparisions:

``` r
summary(HRanalytics)
```

    ##  satisfaction_level last_evaluation  number_project  average_montly_hours
    ##  Min.   :0.0900     Min.   :0.3600   Min.   :2.000   Min.   : 96.0       
    ##  1st Qu.:0.4400     1st Qu.:0.5600   1st Qu.:3.000   1st Qu.:156.0       
    ##  Median :0.6400     Median :0.7200   Median :4.000   Median :200.0       
    ##  Mean   :0.6128     Mean   :0.7161   Mean   :3.803   Mean   :201.1       
    ##  3rd Qu.:0.8200     3rd Qu.:0.8700   3rd Qu.:5.000   3rd Qu.:245.0       
    ##  Max.   :1.0000     Max.   :1.0000   Max.   :7.000   Max.   :310.0       
    ##                                                                          
    ##  time_spend_company Work_accident         left       
    ##  Min.   : 2.000     Min.   :0.0000   Min.   :0.0000  
    ##  1st Qu.: 3.000     1st Qu.:0.0000   1st Qu.:0.0000  
    ##  Median : 3.000     Median :0.0000   Median :0.0000  
    ##  Mean   : 3.498     Mean   :0.1446   Mean   :0.2381  
    ##  3rd Qu.: 4.000     3rd Qu.:0.0000   3rd Qu.:0.0000  
    ##  Max.   :10.000     Max.   :1.0000   Max.   :1.0000  
    ##                                                      
    ##  promotion_last_5years         sales         salary    
    ##  Min.   :0.00000       sales      :4140   high  :1237  
    ##  1st Qu.:0.00000       technical  :2720   low   :7316  
    ##  Median :0.00000       support    :2229   medium:6446  
    ##  Mean   :0.02127       IT         :1227                
    ##  3rd Qu.:0.00000       product_mng: 902                
    ##  Max.   :1.00000       marketing  : 858                
    ##                        (Other)    :2923

``` r
## there are several ways of looking at grouped data [Fastest]
table(HRanalytics$sales)
```

    ## 
    ##  accounting          hr          IT  management   marketing product_mng 
    ##         767         739        1227         630         858         902 
    ##       RandD       sales     support   technical 
    ##         787        4140        2229        2720

``` r
## dpylr
HRanalytics %>% 
  count(left) 
```

    ## # A tibble: 2 × 2
    ##    left     n
    ##   <int> <int>
    ## 1     0 11428
    ## 2     1  3571

``` r
## plotting
plot(HRanalytics$salary)
```

![]({{ site.url }}/img/data_analysis/hr_dataset/unnamed-chunk-7-1.png)

``` r
## pairs [Slowest]
pairs(HRanalytics)
```

Predictive Analytics) Employee Retention
----------------------------------------

Training and Testing

``` r
##20, 80% split
train=HRanalytics[1:12000,]
test=HRanalytics[12001:nrow(HRanalytics),]
```

### Decision Trees

``` r
fit = rpart(left~satisfaction_level+last_evaluation+number_project+average_montly_hours+time_spend_company+promotion_last_5years+sales+salary,data=train,method="class")
pred = predict(fit,test)
```

``` r
summary(fit)
```

``` r
## 0 = stayed, 1 = left
rpart.plot(fit, extra = 2, shadow.col ="gray")
```

![]({{ site.url }}/img/data_analysis/hr_dataset/unnamed-chunk-12-1.png)

Now we need to test its accuracy

``` r
printcp(fit)
```

    ## 
    ## Classification tree:
    ## rpart(formula = left ~ satisfaction_level + last_evaluation + 
    ##     number_project + average_montly_hours + time_spend_company + 
    ##     promotion_last_5years + sales + salary, data = train, method = "class")
    ## 
    ## Variables actually used in tree construction:
    ## [1] average_montly_hours last_evaluation      number_project      
    ## [4] satisfaction_level   time_spend_company  
    ## 
    ## Root node error: 2000/12000 = 0.16667
    ## 
    ## n= 12000 
    ## 
    ##        CP nsplit rel error xerror      xstd
    ## 1 0.16400      0    1.0000 1.0000 0.0204124
    ## 2 0.06375      3    0.4220 0.4220 0.0140057
    ## 3 0.05400      6    0.2270 0.2290 0.0104943
    ## 4 0.02000      7    0.1730 0.1750 0.0092167
    ## 5 0.01700      8    0.1530 0.1685 0.0090490
    ## 6 0.01050      9    0.1360 0.1395 0.0082540
    ## 7 0.01000     10    0.1255 0.1330 0.0080639

### Random Forest

``` r
fit2 <- randomForest(left~satisfaction_level+last_evaluation+number_project+average_montly_hours+time_spend_company+promotion_last_5years+sales+salary,data=train)
```

    ## Warning in randomForest.default(m, y, ...): The response has five or fewer
    ## unique values. Are you sure you want to do regression?

``` r
print(fit2)
```

    ## 
    ## Call:
    ##  randomForest(formula = left ~ satisfaction_level + last_evaluation +      number_project + average_montly_hours + time_spend_company +      promotion_last_5years + sales + salary, data = train) 
    ##                Type of random forest: regression
    ##                      Number of trees: 500
    ## No. of variables tried at each split: 2
    ## 
    ##           Mean of squared residuals: 0.01532125
    ##                     % Var explained: 88.97

``` r
importance(fit2)
```

    ##                       IncNodePurity
    ## satisfaction_level        526.17718
    ## last_evaluation           194.39069
    ## number_project            295.31888
    ## average_montly_hours      246.58314
    ## time_spend_company        281.10927
    ## promotion_last_5years       1.69423
    ## sales                      23.11345
    ## salary                     13.82964

``` r
plot(fit2)
```

![]({{ site.url }}/img/data_analysis/hr_dataset/unnamed-chunk-16-1.png)

``` r
fit3 = rpart(left~satisfaction_level+number_project+average_montly_hours+time_spend_company,data=train,method="class")
pred = predict(fit,test)
```

``` r
## 0 = stayed, 1 = left
rpart.plot(fit3, extra = 2, shadow.col ="gray")
```

![]({{ site.url }}/img/data_analysis/hr_dataset/unnamed-chunk-18-1.png)

Overall, based on what we've learned from our tree models is that satisfaction\_level plays the highest factor in predicting whether a employee leaves or not. It is then followed by number of projects given, time spent at the company, and average\_monthly\_hours. We know that employees would start to leave under these conditions. 4 or more projects with low satisfaction and 3 projects with extremely low satisfaction. The other condition is people working on less projects, but have incurred alot of overtime.

### Data Visualization

GGPlot

``` r
ggplot(HRanalytics, aes(x = satisfaction_level)) +
geom_density(aes(colour=salary, fill=salary, alpha=.5))
```

![]({{ site.url }}/img/data_analysis/hr_dataset/unnamed-chunk-19-1.png)

``` r
ggplot(HRanalytics, aes(satisfaction_level, average_montly_hours, left))+ geom_density2d(aes(color = factor(left)))
```

![]({{ site.url }}/img/data_analysis/hr_dataset/unnamed-chunk-20-1.png)
