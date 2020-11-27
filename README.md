# Scripts to set up app server #

Templates need to be first filled with information and saved without the .template suffix in their filename

    1. config/app_config.env.template
    2. inventory.template
    3. vars/sensitive.yml.template
    4. vars/default.yml.template

Add chain.pem file in folder - config

    This is required for services to access Kafka Server

To set up passwordless sudo access using ssh keys on server

    $ ansible-playbook setup.yml

To set up docker on server

    $ ansible-playbook install_docker.yml

To avoid docker bypassing UFW, follow: https://stackoverflow.com/a/58098930
Look at file: ufwrules_notes for example file

To deploy apps on server

    $ ansible-playbook install_app.yml


## Steps to add a new service to the platform ##

    1. add the repository cloning info install_app.yml
    2. update docker-compose.prod.yml with new service and expose required port
    3. update nginx/nginx.conf for required routing to container

