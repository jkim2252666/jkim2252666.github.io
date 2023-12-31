```
layout: single
title: "HR counts among three legendary hitters"
```

```R
#If Lahman library is the first time, install the package.
#install.packages("Lahman")
```

    Installing package into 'C:/Users/jaeminkim/AppData/Local/R/win-library/4.3'
    (as 'lib' is unspecified)
    
    

    package 'Lahman' successfully unpacked and MD5 sums checked
    
    The downloaded binary packages are in
    	C:\Users\jaeminkim\AppData\Local\Temp\Rtmp6Z9kr5\downloaded_packages
    


```R
library(Lahman)
a<-subset(Batting,playerID=="rodrial01"|playerID=="pujolal01"|playerID=="mcgwima01")
with(a,boxplot(HR~playerID))

```


    
![png](output_1_0.png)
    



```R
a$name<-with(a, ifelse(playerID=="rodrial01","Rodriguez",
                       ifelse(playerID=="pujolal01","Pujols","McGuire")))
with(a,boxplot(HR~name,xlab="Hitter"))
```


    
![png](output_2_0.png)
    

