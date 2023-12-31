---
layout: single
title:  "HR comparison among three legendary hitters"
---

```R
#If Lahman library is the first time, install the package.
#install.packages("Lahman")
```
    
```R
library(Lahman)
a<-subset(Batting,playerID=="rodrial01"|playerID=="pujolal01"|playerID=="mcgwima01")
with(a,boxplot(HR~playerID))
```
    
![no label] (https://github.com/jkim2252666/jkim2252666.github.io/blob/master/_posts/hr_no_label.png)
    

```R
a$name<-with(a, ifelse(playerID=="rodrial01","Rodriguez",
                       ifelse(playerID=="pujolal01","Pujols","McGuire")))
with(a,boxplot(HR~name,xlab="Hitter"))
```


    
![label] (https://github.com/jkim2252666/jkim2252666.github.io/blob/master/_posts/hr_label.png)
    

