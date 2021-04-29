## 1. Getting Started
Welcome to our workshop on using CubSFS to generate a demographic reconstruction based on a SFS (allele/site frequency spectrum). Alana will give you a brief spiel about what a SFS is and a general description of how this analysis works in just a sec, but first, let's download R and R Studio , so the installation can proceed while she's prattling on.  

### A) Installing R
First off, we need to install R (if it isn't already on your computer). After heading to: 
https://cran.rstudio.com/
Select your operating system, download, and install R however you install things on your operating system.

### B) Downloading R Studio
Although we could run our code directly in R, R Studio is a neat little GUI that allows you to save the code that you are writing for later reuse. Download R Studio (if it isn't already on your computer) at: `https://www.rstudio.com/products/rstudio/download/`  
Download the RStudio Desktop Open Source License version that matches your operating system (note, can be quite a big download e.g. 150MB!), and then install R Studio however you install things on your operating system.

### C) Downloading the CubSFS package
Our next step is to download the CubSFS package. This package has additional functions that we'll use to do our demographic reconstructions. Head to:
https://github.com/blwaltoft/CubSFS/blob/master/CubSFS_1.0.tar.gz
and click on the `Download` button

### D) Installing the CubSFS package
First up, we need to install *another* package that CubSFS needs in order to function, `nloptr`. After opening R Studio, into the main console window, type:
`install.packages("nloptr")`
<img width="100%" src="../Images/Install_nloptr.png">

Now we are ready to install CubSFS. To do this:  
    - Go to `Tools`.  
    - Go to `Install Packages`.  
    - In the `Install From` drop down menu select Package Archive File (.zip; .tar.gz)  
    - Browse your way to the CubSFS_1.0.tar.gz file (note, you don't need to `untar` it...also don't worry if you don't know what `untar` means!)  
<img width="100%" src="../Images/Install_packages_menu.png">
    - Click on `Install`

We are ready to load all the functions with the CubSFS package into this R session so they are available for us to use (installing the package is like buying a book and putting it on a shelf, loading the package is like getting the book out to read). Keeping with the book analogy, the command for loading in the package is:
`library(cubSFS)`
<img width="100%" src="../Images/Library_cubSFS.png">



