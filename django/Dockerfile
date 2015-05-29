# Build the Purple Robot Django Endpoint Webapp

# From base Django image
#FROM django:onbuild
FROM tutum/apache-php

# Maintainer
MAINTAINER "Amos A Folarin <amosfolarin@gmail.com>"

# Add Dependancies
RUN sudo apt-get update && \
    sudo apt-get -yq install python-setuptools \ 
                                libapache2-mod-wsgi \
                                git && \
    sudo easy_install virtualenv && \
    easy_install django    

# Add Purple Robot project parts
RUN cd /tmp && \
	git clone https://github.com/KHP-Informatics/Purple-Robot-Django_Main.git && \
    git clone https://github.com/KHP-Informatics/Purple-Robot-Django.git

# Add Purple Robot django project folder
RUN mkdir /var/www/django/ && \
	cp -r /tmp/Purple-Robot-Django_Main/purple_robot /var/www/django/ && \
	cp -r /tmp/Purple-Robot-Django_Main/venv /var/www/django/ && \
    mkdir /var/www/django/purple_robot/purple_robot_app && \
    cp -r /tmp/Purple-Robot-Django/* /var/www/django/purple_robot/purple_robot_app

# Parse environmental variables file



