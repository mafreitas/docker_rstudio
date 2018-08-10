FROM rocker/rstudio-stable:3.5.1
## Work-around to make Docker Hub use the Dockerfile from https://github.com/rocker-org/rocker-versioned/rstudio
## docker build -t mfreitas/rstudio_351_edger:0.1 .
## docker run --rm -it -p 8787:8787 -v $(pwd):/home/$USER/data -e USER=$USER -e USERID=$UID mfreitas/rstudio_351_edger:0.1

RUN apt-get update && \
  apt-get install -y libxml2-dev libz-dev libpq-dev libmysql++-dev libssh2-1-dev && \
  rm -rf /var/lib/apt/lists/*

RUN R -e "source('https://bioconductor.org/biocLite.R')" \
  && install2.r --error \
    --deps TRUE \
    -r 'http://cran.rstudio.com' \
    -r 'https://www.bioconductor.org/packages/release/bioc' \
    tidyverse \
    dplyr \
    devtools \
    stringr \
    shinydashboard \
    edgeR \
    qvalue \
    DT

## TODO
##
