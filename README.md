# Testing microservices with Laravel

This proyect is fully dedicated to testing microservices with Laravel.

## Tech

The tecnologies to use:

- Docker
- Laravel 8.x
- Mysql
- Mongo
- PHP
- Nginx
- Composer
- Phpmyadmin


## Installation

Install the dependencies and devDependencies and start the server.

# Cleate the src directory
```sh
mkdir src
cd <path to project>/src
```
# Install Laravel
```sh
composer create-project --prefer-dist laravel/laravel:^8.0 helloworld
```
# Laravel Configurations
```sh
cd <path to project>/src/helloworld
```
```sh
# Update .env
....
....
DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=helloworld
DB_USERNAME=root
DB_PASSWORD=password
```
# Build
```sh
cd <path to project>
docker-compose build
```
# Launch Application
```sh
docker-compose up
```
# List Files
```sh
cd <path to project>/src/helloworld
docker-compose exec php ls -l
```
# Example
```sh
docker-compose exec php php artisan migrate
```
# MongoDB Extension for Laravel
```sh
composer require jenssegers/mongodb:^3.8 --ignore-platform-reqs
```
 Update .env
```sh
MONGO_CONNECTION=mongodb
MONGO_HOST=mongo
MONGO_PORT=27017
MONGO_AUTH_DATABASE=admin
MONGO_DATABASE=helloworld
MONGO_USERNAME=root
MONGO_PASSWORD= password
```
# /config/database.php
```sh
'mongodb' => [
            'driver'   => 'mongodb',
            'host'     => env('MONGO_HOST'),
            'port'     => env('MONGO_PORT'),
            'database' => env('MONGO_DATABASE'),
            'username' => env('MONGO_USERNAME'),
            'password' => env('MONGO_PASSWORD'),
            'options'  => [
                'database' => env('MONGO_AUTH_DATABASE')
            ]
        ],
```
#  config/app.php
```sh
'providers' => [


		Jenssegers\Mongodb\MongodbServiceProvider::class
    ],
```


## Plugins

List of services


| Service | Url |
| ------ | ------ |
| Laravel | http://localhost |
| Phpmyadmin | http://localhost:8085] |
| Mongodb | http://localhost:8081] |

## License

MIT

**Free Software, Hell Yeah!**
