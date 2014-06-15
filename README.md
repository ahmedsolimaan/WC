Brazil’s Host Advantage in WC 2014
==

This R script calculate probability of winning the world cup on whether the country was the host and also if the county was not the host but located in the same continent (I merge North and South America for this exercise)

The original source of this script [here](http://diffuseprior.wordpress.com/2014/06/13/brazils-host-advantage/)

I updated the excel to add the continent and hosts data. The result is not exactly the same but it is very close.

**Packages Required**

    > library(rJava)
    > library(xlsxjars)
    > library(xlsx)
    > library(mfx)
 

**R Code**

    > wc <- read.xlsx("./data/wc.xlsx",sheetIndex=1, header=TRUE)
 
    > probitmfx(formula=winners ~ continent + hosts, data=wc)
    Call:
    probitmfx(formula = winners ~ continent + hosts, data = wc)
    
    Marginal Effects:
     dF/dx Std. Err.  zP>|z|   
    continent 0.041983  0.025183 1.6671 0.095485 . 
    hosts 0.372162  0.126570 2.9404 0.003278 **
    ---
    Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
    
    dF/dx is for discrete change for the following variables:
    
    [1] "continent" "hosts"
