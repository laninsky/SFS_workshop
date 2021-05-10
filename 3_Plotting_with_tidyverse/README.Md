## Plotting results using ggplot2
We will use `ggplot2`, part of the tidyverse package, to "bling" up our plots of demographic history through time.
```
# Defining our data as last_50k$Ntdf
ggplot(last_50k$Ntdf) +
    # Creating a blue ribbon for the confidence interval
    geom_ribbon(aes(x=time,ymin=LCL,ymax=UCL),fill="blue",,alpha=0.6,color="black",size=0.5) +
        # Using a dashed line to represent the median of the bootstrap replicates 
        geom_line(aes(x=time,y=median),color="black",linetype="dashed",size=0.5) + 
            # Using a solid line for the CubSFS trajectory for our observed SFS
            geom_line(aes(x=time,y=Nt),color="black",size=0.5) +
                # Blinging up the plot by modifying the theme
                theme_bw(base_size = 6) + ylab("Effective population size") + xlab ("Time")
```
If you get through all of this, some extension exercises:
(1) Try plotting your `last_million` results instead 
(2) Run a few more bootstrap replicates through `CubSFS` and regenerate the results (e.g. `last_50k`) to see how that affects the plot.
(3) Experiment with the `time_points` (`knots`) and `oldest_time` (`t_m`) to see how that impacts on the demographic reconstruction and/or the AIC values.
