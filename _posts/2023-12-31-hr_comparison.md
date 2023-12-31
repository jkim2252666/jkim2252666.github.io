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
    
![no label](/jkim2252666.github.io/_posts/hr_no_label.png)
    

```R
a$name<-with(a, ifelse(playerID=="rodrial01","Rodriguez",
                       ifelse(playerID=="pujolal01","Pujols","McGuire")))
with(a,boxplot(HR~name,xlab="Hitter"))
```


    
![label](/jkim2252666.github.io/_posts/hr_label.png)
    

