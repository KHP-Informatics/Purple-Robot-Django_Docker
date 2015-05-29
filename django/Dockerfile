# Build the Purple Robot Django Endpoint Webapp

# From base Django image
FROM django:onbuild

# Maintainer
MAINTAINER "Amos A Folarin <amosfolarin@gmail.com>"

# Add Dependancies


# Add Purple Robot project parts
RUN mkdir -p /var/www/django/ && \
        chmod 755 /var/www/django /var/www/ && \


# Add Purple Robot django project folder
RUN cd /var/www/django/ && \
	git clone https://github.com/KHP-Informatics/Purple-Robot-Django_Main.git && \
	cd /var/www/django/Purple-Robot-Django_Main/purple_robot/ && \
    git clone https://github.com/KHP-Informatics/Purple-Robot-Django.git
    
#   mv /var/www/django/Purple-Robot-Django_Main /var/www/django/purple_robot && \
#	mv /var/www/django/purple_robot/Purple-Robot-Django /var/www/django/purple_robot/purple_robot_app


# Parse environmental variables file



