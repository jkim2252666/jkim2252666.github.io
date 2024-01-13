---
layout: single
title:  "Boxplots for comparing homeruns"
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
    
![image](https://github.com/jkim2252666/statistics_with_mlb/assets/67861374/f1caae62-7dc6-4a24-a7ca-02b15cf670c6)
    

```R
a$name<-with(a, ifelse(playerID=="rodrial01","Rodriguez",
                       ifelse(playerID=="pujolal01","Pujols","McGuire")))
with(a,boxplot(HR~name,xlab="Hitter"))
```
![image](https://github.com/jkim2252666/statistics_with_mlb/assets/67861374/64a55371-2293-4bed-a737-a4912413fe2e)


    

    

