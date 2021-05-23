# Jupyterhub-Rstudio-Sever

#Creamos un droplet en Digital Ocean  con Ubuntu 20.4 al menos 2gb de ram y lo iniciamos

wget https://raw.githubusercontent.com/jupyterhub/the-littlest-jupyterhub/master/bootstrap/bootstrap.py

python3 bootstrap.py --admin dan-robles

#Listo esperamos 10 minutos y reiniciamos el drolpets

#Ahora instalamos R 

sudo add-apt-repository 'deb https://cloud.r-project.org/bin/linux/ubuntu focal-cran40/'

# Instalamos la llaves
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys E298A3A825C0D65DFD57CBB651716619E084DAB9
sudo apt update

#Instalamos paqetes necesarios para R
sudo apt install r-base r-base-core r-recommended r-base-dev

sudo add-apt-repository ppa:c2d4u.team/c2d4u4.0+
sudo apt update

sudo apt install r-cran-rgl r-cran-rjags r-cran-snow r-cran-ggplot2 r-cran-igraph r-cran-lme4 r-cran-rjava r-cran-devtools r-cran-roxygen2 r-cran-rjava

#Paquetes para analisis espacial
sudo apt install libgdal-dev libproj-dev libgeos-dev libudunits2-dev libnode-dev libcairo2-dev libnetcdf-dev
sudo apt install libglu1-mesa-dev freeglut3-dev mesa-common-dev

#Instalamos Rstudio Server
sudo apt-get install gdebi-core
wget https://download2.rstudio.org/server/bionic/amd64/rstudio-server-1.4.1106-amd64.deb
sudo gdebi rstudio-server-1.4.1106-amd64.deb
sudo adduser rstudio

#Instalamos Shiny Server
sudo su - \
-c "R -e \"install.packages('shiny', repos='https://cran.rstudio.com/')\""

sudo apt-get install gdebi-core
wget https://download3.rstudio.org/ubuntu-14.04/x86_64/shiny-server-1.5.16.958-amd64.deb
sudo gdebi shiny-server-1.5.16.958-amd64.deb


