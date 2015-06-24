# Postgres container for the Purple Robot Django project


#Base db container on tutum postgres container
#FROM tutum/postgresql  #need postgresql9.4, tutum on trusty so only 9.3 in repo
FROM afolarin/postgres:v9.4

#maintainer
MAINTAINER "Amos A Folarin <amosfolarin@gmail.com>"

#Load in clean purple robot warehouse database
RUN apt-get update && \
    apt-get -y install sysv-rc-conf

# mount a volume for the db (I used /mnt/pr/data)
#ENV PG_DATA_DIR="/mnt/pr/data"
#RUN mkdir -p ${PG_DATA_DIR} && \
#        chown postgres:postgres ${PR_DATA_DIR}

#VOLUME ["/mnt/pr/data"]

# stop the postgres server and
# start it with the mounted data directory provided by the mounted volume
#RUN sudo service postgres stop && \
#    sudo su - postgres && \
#    /usr/lib/postgresql/9.4/bin/initdb -U postgres -D ${PG_DATA_DIR} 


#start the postgres postmaster daemon
#RUN service postgresql initdb -U postgres -D ${PG_DATA_DIR}

# configure the postgres server to start at boot
RUN sysv-rc-conf postgresql on
# Enable MD5 authentication. Edit /etc/postgresql/9.4/main/pg_hba.conf Add the following line:
#cat >> /etc/postgresql/9.4/main/pg_hba.conf <<< "host all all 127.0.0.1/32 md5"
#cat >> /etc/postgresql/9.4/main/pg_hba.conf <<< "host all all * md5"
# NOTE: when the db container is created it will accept connections from all ip addresses 
# which you probably don't want, users should constrain this by adding the appropriate IP address into
# /etc/postgresql/9.4/main/pg_hba.conf e.g. modify 
# host all all * md5
# to
# host all all <prweb-container-ipaddress>/32 md5

# add /etc/postgresql/9.4/main/postgresql.conf to include:
#cat >> /etc/postgresql/9.4/main/postgresql.conf <<< 'listen_addresses = "*"'

# restart the postgres server
#service postgresql restart


