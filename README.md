This is a stub for running Laravel applications in Docker containers.
Available: Composer, Artisan, NPM & PostgreSQL.

## Preparing for launch
#### .env
Copy the **.env.example** file to **.env** and customize it. The **APP_KEY** section will be configured below.

#### Installing dependencies
```
bin/composer install
bin/npm install
```
#### Running migrations
To run migrations, you need to start the app.
```
bin/up
```
After start the migrations.
```
bin/artisan migrate
```
#### Create a symlink for storage.
```
bin/artisan storage:link
```
#### Generate an application key.
Run command:
```
bin/artisan key:generate --show
```
Then enter the generated key in the .env file in the **APP_KEY** section

## Running
Run command:
```
bin/up
```
or to run in the background:
```
bin/up -d
```
This is an alias for the docker compose up command.

After a successful build and run, the application will be available at **localhost:PORT,** where **PORT** is the port specified in the **.env** file in the **APP_PORT** section.

After an update (e.g. git pull) you will need to rebuild the containers on startup::
```
bin/up --build
```

## Running frontend for dev
Run command:
```
bin/npm run dev
```

## Building frontend
Run command:
```
bin/npm run build
```


## Available commands
### Composer
Running composer command (require, install etc.).

```
bin/composer <command>
```
### Artisan
Running laravel artisan command (migrate, make etc.).

```
bin/artisan <command>
```
### Pint
Running laravel pint.

```
bin/pint
```
### NPM
Running npm for installing packages, running in dev mode or building.

```
bin/npm <command>
```
### Up
Launches all the necessary containers for the application to work.

```
bin/up -d
```
### Down
Stops all containers.

```
bin/down
```