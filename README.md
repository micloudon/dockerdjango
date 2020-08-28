Here is a very basic Docker project. The goal is to get a django development server up and running.


initialize the project:

    sudo docker-compose run web django-admin startproject testsite . 

Once the project installed, you'll need to change permissions

Change permissions:

    sudo chown -R $USER:$USER .

Next we'll run this project

Run project:

    sudo docker-compose up

Now we will access our site:
    Paste http://127.0.0.1:8000/ or http://localhost:8000/ into your browser

We're going to create a new app in our project:

    docker exec *container name* python manage.py startapp *appname

        **my container name is 'docker_web_1'
        *my app name is hello

A new folder will be created.

You may need to update your permissions:

    sudo chown -R $USER:$USER .


Now you have an a django environment up and running inside a docker container.

A few thing to consider; you may want to add a migration section to the docker-compose.yml file because realistically any django project will have migrations that will need to be made.
