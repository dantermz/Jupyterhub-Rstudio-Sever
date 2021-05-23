# Jupyterhub-Rstudio-Sever

#Creamos un droplet en Digital Ocean  con Ubuntu 20.4 al menos 2gb de ram y lo iniciamos

wget https://raw.githubusercontent.com/jupyterhub/the-littlest-jupyterhub/master/bootstrap/bootstrap.py

python3 bootstrap.py --admin dan-robles

#Listo esperamos 10 minutos y reiniciamos el drolpets

#Ahora instalamos R 

sudo add-apt-repository 'deb https://cloud.r-project.org/bin/linux/ubuntu focal-cran40/'
