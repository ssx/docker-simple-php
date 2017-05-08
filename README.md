# Simple PHP for Docker

This project will drop in to an existing project and run it within Docker. It
comes with the latest version of PHP-FPM, Nginx, MariaDB, Beanstalk, Redis and
Mailhog for when you're using it in local development.


### Getting Started in 1 seconds

Clone this repository and run `docker-compose up` then point your browser at
`http://localhost:8080` and you should see a beautiful PHP info page.


### Getting Started in 5 seconds

Clone this repository to your local machine. Copy the `docker-compose.yml`
file and `.docker` directory into your project directory. Then run
`docker-compose up` and you'll be off and running.


### Getting started in 30 seconds

Clone this repository, sit around for 26 seconds then do the step above.


### MariaDB/MySQL Password

The default root password is `vagrant` and the default database name is `vagrant`,
both of these should be changed to suit your project. The data will be persisted
across containers being created/destroyed in the `.docker/volumes/mysql`
directory on your local machine (or server you deploy to).


### nginx

You can overwrite the Nginx website config by editing the file that is located at
`.docker/config/nginx.conf` which will be picked up on starting the container.


### PHP

The included version of PHP-FPM includes GD, Intl and BZ2 extensions as well as
Composer being installed as well.


### Accessible URLs

You can access the services Nginx, MariaDB, Mailhog and Beanstalkd Console at:

 - Nginx - http://localhost:8080
 - mailhog - http://localhost:8081
 - Beanstalkd Console - http://localhost:8082
 - MariaDB - tcp://localhost:3306 (Use Sequel Pro on a Mac)


### Hosts

When configuring your environment to connect to each service, you can use the
following hostnames and ports:

  - `mariadb` - 3306
  - `beanstalkd` - 11300
  - `redis` - 6739
  - `mailhog` - 1025


### Accessing PHP within the stack

If you're running something like Laravel and need to run `php artisan migrate`, you can 
do this by running:

   `docker-compose exec php bash`
   
within the project directory, this will give you a bash prompt that you can then `cd /www` 
and run `php artisan migrate` and it'll run the migrations.

### License

This project is licensed under an Apache 2.0 license which you can find within
this repository in the [LICENSE file](https://github.com/ssx/docker-simple-php/blob/master/LICENSE).


### Feedback

If you have any feedback, comments or suggestions, please feel free to open an
issue within the repository on [Github](https://github.com/ssx/docker-simple-php).
