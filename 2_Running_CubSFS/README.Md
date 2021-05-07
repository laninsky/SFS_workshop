## Running CubSFS
If you've jumped straight to this section, please make sure that you've got `R` and `R studio` installed, as well as loading the packages `tidyverse`, `parallel`, and `cubSFS` (see [1_Getting_Started](../1_Getting_Started/README.Md) for instructions on installing `cubSFS`). Every time you restart `R studio`/load `cubSFS`, you'll also need to source the modified `cubSFS` code from wherever you downloaded it e.g.
```
source("AicCubSFS.R")
source("CValpha.R")
source("estimateAlpha.R")
source("estimateCubSFS.R")
```

### A) Downloading the SFS file
```
download.file("https://raw.githubusercontent.com/laninsky/SFS_workshop/main/Data_Scripts/NZ_Gaus_pop1_MAFpop0.obs","lamprey_sfs.txt")
```

### B) Loading the SFS file in
```
# Reading in the file, skipping the first line
obsSFS <- read_table2("lamprey_sfs.txt",skip = 1)

#  Converting the file to a matrix
obsSFS <- as.matrix(obsSFS)[1,]

# Rounding the entries as CubSFS can have problems with decimals
obsSFS <- round(obsSFS,digits=0)
```

### C) Setting some parameters for the analysis
```
# mutation rate in sites/gen
mu <- 5e-08

# generation time per year
genyr <- 14

# the number of time points the reconstruction will be sliced up into
time_points <- 29

# oldest time point in coalescent units (1 coalescent unit = 2Ne generations)
oldest_time <- 0.25
```

### D) Obtaining a few parameters we'll need from the SFS file
```
# Number of samples
n.samples <- length(obsSFS)

# Total number of sites in SFS
# We'll need this number for converting our estimates into absolute time
total.nb.sites <- sum(obsSFS)

# Removing the monomorphic sites for estimating the relative demography of the population
obsSFS <- obsSFS[-1]

# As this is a folded matrix, removing the empty entries
obsSFS <- obsSFS[1:(length(obsSFS)/2)]
```

### E) Running CubSFS
```

```