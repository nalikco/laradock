# Laravel Docker Stub

First of all, you need to copy the ```.env.example``` to ```.env``` and configure it.

Inside the PHP container you need to run the following commands:
```shell
php artisan migrate # running migrations
php artisan storage:link # creating a symbolic link to the storage folder
```

The data is stored in the ```data``` folder at the level above the project:
```shell
../data/db # database folder
../data/uploads # app uploads folder (storage/app/public)
```

Running for development:
```shell
bin/dev/up
```

Building for development:
```shell
bin/dev/build
```

Running for production:
```shell
bin/prod/up
```

Building for production:
```shell
bin/prod/build
```

Entering to container with PHP:
```shell
bin/php-container
```