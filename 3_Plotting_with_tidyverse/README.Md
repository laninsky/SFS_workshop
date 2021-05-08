## Plotting results using ggplot2
We will use `ggplot2`, part of the tidyverse package, to "bling" up our plots of demographic history through time.


### K)
#12. Writing out the 50,000 time scale data so we can pull it back 
# in and plot all the species at the same time after they are done
write.table(resNt$Ntdf,paste(outputfilename,"popsize.txt",sep=""),row.names = FALSE, quote=FALSE)
```