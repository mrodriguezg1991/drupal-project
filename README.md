1 Download project from git

 git clone git@github.com:mrodriguezg1991/drupal-project.git 

2 Access project directory drupal-project

 cd drupal-project/

3 Change .env.exmple to .env

 cp .env.example .env

4 Change the parameters of the connection

 gedit .env

  Example
 	DB_NAME=drupal
	DB_USER=drupal
	DB_PASSWORD=drupal
	DB_ROOT_PASSWORD=password
	DB_HOST=mariadb
	DB_DRIVER=mysql

3 Execute docker containers 

 docker-compose up -d

4 Access php container 

 docker-compose exec php bash

5-Install composer dependencies

 composer install

6 Access root directory

 cd web/

7 Install drupal8 

 ../vendor/drush/drush/drush site-install standard --db-url=mysql://DB_USER:DB_PASSWORD@mariadb/DB_NAME --account-mail="admin@example.com" --account-name=admin --account-pass=some_admin_password --site-mail="admin@example.com" --site-name="Site-Install"

 # the values in the -db-url are the same of the .env file 
 	

8 Import drush configuration

 ../vendor/drush/drush/drush config-import

9 Add to /etc/hosts line 

"127.0.0.1  drupal.docker.localhost" 

10 Go to the site url

http://drupal.docker.localhost:8000
	
