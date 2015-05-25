Example of Apache with Docker
===========

### Apache environment variables
Apache will make of the following environment variables.

	APACHE_SERVERADMIN=admin@localhost
	APACHE_SERVERNAME=localhost
	APACHE_SERVERALIAS=docker.localhost
	APACHE_DOCUMENTROOT=/var/www
	APACHE_RUN_USER=www-data
	APACHE_RUN_GROUP=www-data
	APACHE_LOG_DIR=/var/web/log/apache2
	APACHE_PID_FILE=/var/run/apache2.pid
	APACHE_RUN_DIR=/var/run/apache2
	APACHE_LOCK_DIR=/var/lock/apache2


### Image Base

Ubuntu 14.04


### How to Build

Simply `docker build -t your_image_name https://github.com/dicotraining/docker-sample.git`

That's all

### Start the container
The container has all pre requisites set up to run any apache application. You can specify all needed environment variables.

	$ sudo docker run -i -d -p 80 -e APACHE_SERVERNAME=myServer.local 

Browser to url http://localhost:80.



### Get the container ip and port

    $ sudo docker inspect --format='{{.NetworkSettings.IPAddress}}' <container_id> 
    $ sudo docker port <container_id> 80 | cut -d ":" -f2

Now go to `<your container's ip>:<container's port>` in your browser


### Stop the container

	$ sudo docker stop $(docker ps -ql)`

