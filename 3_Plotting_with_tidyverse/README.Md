## Plotting results using ggplot2
We will use `ggplot2`, part of the tidyverse package, to "bling" up our plots of demographic history through time.
```
# Defining our data as last_50k$Ntdf
ggplot(last_50k$Ntdf) +
    # Creating a blue ribbon for 
    # the confidence interval
    geom_ribbon(aes(x=time,ymin=LCL,ymax=UCL),fill="blue",,alpha=0.6,color="black",size=0.5) +
        # Using a dashed line to 
        # represent the median of
        # the bootstrap replicates 
        geom_line(aes(x=time,y=median),color="black",linetype="dashed",size=0.5) + 
            # Using a solid line for
            # the CubSFS trajectory
            # for our observed SFS
            geom_line(aes(x=time,y=Nt),color="black",size=0.5) +
                # Blinging up the 
                # plot by modifying
                # the theme
                theme_bw(base_size = 6) + ylab("Effective population size") + xlab ("Time")
```
