---
title: Installing R, RStudio, tidyverse, and tinytex
date: "2021-08-01"
menu:
  resource:
    parent: Guides
type: docs
weight: 1
toc: yes
---


**Modified from [Andrew Heiss](https://datavizs21.classes.andrewheiss.com/resource/install/)** 

You will do all of your work in this class with the open source (and free!) programming language [R](https://cran.r-project.org/). You will use [RStudio](https://www.rstudio.com/) as the main program to access R. Here are some instructions for how to get started.


## RStudio.cloud

R is free, but it can sometimes be a pain to install and configure. To make life easier, we are going to use an [RStudio server](rstudio.boisestate.edu), a web-interface to RStudio, that is set up on the Boise State Research Computing cluster. This means you won't have to install anything on your computer to get started with R! We will have a shared folder with the data for exercises and a Github workspace to allow easy access to code and templates.

## RStudio on your computer

At some point you are likely to need a local version of R to run the analyses for your graduate work. Here's how you install all these things

### Install R

First you need to install R itself (the engine).

1. Go to the CRAN (Collective R Archive Network)[^cran] website: <https://cran.r-project.org/>
2. Click on "Download R for `XXX`", where `XXX` is either Mac or Windows:

    <img src="/img/install/install-r-links.png" width="60%" />

    - If you use macOS, scroll down to the first `.pkg` file in the list of files (in this picture, it's `R-4.0.0.pkg`; as of right now, the current version is also 4.0.0) and download it.
    
        <img src="/img/install/install-r-mac.png" width="100%" />
    
    - If you use Windows, click "base" (or click on the bolded "install R for the first time" link) and download it. 
    
        <img src="/img/install/install-r-windows.png" width="100%" />

3. Double click on the downloaded file (check your `Downloads` folder). Click yes through all the prompts to install like any other program.

4. If you use macOS, [download and install XQuartz](https://www.xquartz.org/). You do not need to do this on Windows.

[^cran]: It's a goofy name, but CRAN is where most R packages—and R itself—lives.

### Install RStudio

Next, you need to install RStudio, the nicer graphical user interface (GUI) for R (the dashboard). Once R and RStudio are both installed, you can ignore R and only use RStudio. RStudio will use R automatically and you won't ever have to interact with it directly.

1. Go to the free download location on RStudio's website: <https://www.rstudio.com/products/rstudio/download/#download>
2. The website should automatically detect your operating system (macOS or Windows) and show a big download button for it:

    <img src="/img/install/install-r-rstudio1.png" width="50%" />
    
    If not, scroll down a little to the large table and choose the version of RStudio that matches your operating system.

    <img src="/img/install/install-r-rstudio2.png" width="100%" />

3. Double click on the downloaded file (again, check your `Downloads` folder). Click yes through all the prompts to install like any other program.

Double click on RStudio to run it (check your applications folder or start menu).


### Install `tidyverse`

R packages are easy to install with RStudio. Select the packages panel, click on "Install," type the name of the package you want to install, and press enter.

<img src="/img/install/install-r-package-panel.png" width="40%" />

This can sometimes be tedious when you're installing lots of packages, though. [The tidyverse](https://www.tidyverse.org/), for instance, consists of dozens of packages (including **ggplot2**) that all work together. Rather than install each individually, you can install a single magical package and get them all at the same time.

Go to the packages panel in RStudio, click on "Install," type "tidyverse", and press enter. You'll see a bunch of output in the RStudio console as all the tidyverse packages are installed.

<img src="/img/install/install-r-tidyverse.png" width="60%" />

Notice also that RStudio will generate a line of code for you and run it: `install.packages("tidyverse")`. You can also just paste and run this instead of using the packages panel.

### Install `gdal`
`gdal` is the 'back-end' for most of the spatial packages in R. The easiest way to install `gdal` is to follow the instructions at the `sf` [github page](https://github.com/r-spatial/sf).

### Install `tinytex`

When you knit to PDF, R uses a special scientific typesetting program named LaTeX (pronounced "lay-tek" or "lah-tex"; for goofy nerdy reasons, the x is technically the "ch" sound in "Bach", but most people just say it as "k"—saying "layteks" is frowned on for whatever reason).

LaTeX is neat and makes pretty documents, but it's a huge program—[the macOS version, for instance, is nearly 4 GB](https://tug.org/mactex/mactex-download.html)! To make life easier, there's [an R package named **tinytex**](https://yihui.org/tinytex/) that installs a minimal LaTeX program and that automatically deals with differences between macOS and Windows.

Here's how to install **tinytex** so you can knit to pretty PDFs:

1. Use the Packages in panel in RStudio to install **tinytex** like you did above with **tidyverse**. Alternatively, run `install.packages("tinytex")` in the console.
2. Run `tinytex::install_tinytex()` in the console.
3. Wait for a bit while R downloads and installs everything you need.
4. The end! You should now be able to knit to PDF.
