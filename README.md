# Purple-Robot-Django_Docker
Dockerfile and build instructions for Purple-Robot-Django container and the postgres database container


Container Layout
----------------
 +------------------+
 | Django Container |
 +------------------+
          ^
          |
          |
          V
+-------------------+
| Postgres Container|
+-------------------+



The Components in 3 separate git Repo
-------------------------------------
Purple-Robot-Django_Docker pulls together the other two repositories to build the Django container

```sh
Purple-Robot-Django_Docker #build the Django Container
|
|_ /var/www/django/purple_robot
                    |
                    |__ /Purple-Robot-Django_Main/{purple_robot,venv}  #top level Django project
                    |
                    |__ Purple-Robot-Django{...}  #the principle Django app
                    |
                    |__ ... other Django app extensions
```





