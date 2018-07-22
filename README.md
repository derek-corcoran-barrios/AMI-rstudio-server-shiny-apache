## Setup

### Installing R and R server

#### Installing R

R is a fast-moving project, and the latest stable version isn't always available from Ubuntu's repositories, so we'll start by adding the external repository maintained by CRAN:

`sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys E298A3A825C0D65DFD57CBB651716619E084DAB9`

Once we have the trusted key in each server’s database, we can add the repository.

`sudo add-apt-repository 'deb [arch=amd64,i386] https://cran.rstudio.com/bin/linux/ubuntu xenial/'`

We'll need to run update after this in order to include package manifests from the new repository:

`sudo apt-get update`

If the lines above appear in the output from the update command, we've successfully added the repository. We can be sure we won't accidentally install an older version.

Now we're ready to install R:

`sudo apt-get install r-base`

#### Downloading and installing RStudio Server

To download and install RStudio Server open a terminal window and execute the following commands. Note that the gdebi-core package is installed first so that gdebi can be used to install RStudio and all of its dependencies.

`sudo apt-get install gdebi-core`

`wget https://download2.rstudio.org/rstudio-server-1.1.456-amd64.deb`

This might not be the latest RStudio Server version, please check the following [link](https://www.rstudio.com/products/rstudio/download-server/)

`sudo gdebi rstudio-server-1.1.456-amd64.deb`

Once you have done this don't forget to add an HTPP security group for port 80 in AWS and an *Custom TCP* for port 8787 (default for Rstudio-server) with **source::anywhere**, now you can use Rstudio-server

