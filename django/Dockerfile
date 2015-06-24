# Build the Purple Robot Django Endpoint Webapp

# From base Django image
#FROM django:onbuild
FROM tutum/apache-php

# Maintainer
MAINTAINER "Amos A Folarin <amosfolarin@gmail.com>"

# Add Dependancies
RUN sudo apt-get update && \ 
    apt-get install -y python-numpy \
    python-dev \
    virtualenv \
    python-pip \
    libpq-dev 

# Add Purple Robot django project folder
RUN mkdir -p /var/www/django/ && \
    chmod 755 /var/www/django /var/www/ && \
    cd /tmp
    git clone https://github.com/KHP-Informatics/Purple-Robot-Django_Main.git && \
    git clone https://github.com/KHP-Informatics/Purple-Robot-Django.git && \
    mv /tmp/Purple-Robot-Django_Main/purple_robot /var/www/django/ && \
    mv /tmp/Purple-Robot-Django/purple_robot_app /var/www/django/purple_robot
    

        
RUN sudo pip install virtualenv && \
    pip install -r /var/www/django/purple_robot/purple_robot/requirements.pip && \
    virtualenv /var/www/django/venv 


#Config Apache
RUN cat << EOF >> /etc/apache2/sites-available/000-default.conf << \
    '# For most configuration files from conf-available/, which are \
       # enabled or disabled at a global level, it is possible to \
       # include a line for only one particular virtual host. For example the \
       # following line enables the CGI configuration for this host only \
       # after it has been globally disabled with "a2disconf". \
       #Include conf-available/serve-cgi-bin.conf \
       WSGIDaemonProcess purple-robot python-path=/var/www/django/venv/lib/python2.7/site-packages:/var/www/django/purple_robot \
       WSGIProcessGroup purple-robot\ 
       WSGIScriptAlias / /var/www/django/purple_robot/purple_robot/wsgi.py \
       Alias /media /var/www/django/purple_robot/media \
       Alias /static /var/www/django/purple_robot/static' \
    EOF && \
    sudo service apache2 restart

#Config Django  *NOTE* May have to create intermediate image --> Django admin user create req manual step..... or use --noinput
RUN cd  /var/www/django/purple_robot/purple_robot/ && \
    rm purple_robot_app/migrations && \
    python manage.py syncdb --migrate --noinput
    sudo service apache2 restart



#   mv /var/www/django/Purple-Robot-Django_Main /var/www/django/purple_robot && \
#	mv /var/www/django/purple_robot/Purple-Robot-Django /var/www/django/purple_robot/purple_robot_app


# Parse environmental variables file



