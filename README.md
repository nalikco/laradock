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
