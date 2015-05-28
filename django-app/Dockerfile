# Build the Purple Robot Django Endpoint Webapp

# From base Django image
FROM django:onbuild

# Maintainer
MAINTAINER "Amos A Folarin <amosfolarin@gmail.com>"

# Add Dependancies


# Add Purple Robot project parts
ADD ./manage.py /var/www/django/purple_robot/
ADD ./static /var/www/django/purple_robot/
RUN mkdir media && \




# Add Purple Robot django project folder
RUN cd /var/www/django && \
	git clone https://github.com/KHP-Informatics/Purple-Robot-Django_Main.git && \
	git clone https://github.com/KHP-Informatics/Purple-Robot-Django.git 
	


# Parse environmental variables file



