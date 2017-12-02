# learning_laravel

## Server

### Start PHP Server on c9

`php -S 0.0.0.0:8080 -t public/`

## Laravel

### Create new laravel project

```
composer global require "laravel/installer=~1.1"
composer create-project laravel/laravel myapp
```

### Generate Key

`php artisan key:generate`

### Serve Laravel App

`php artisan serve`

### Create Model/Controller/Migrations/Resources

`php artisan make:model Task --migration --controller --resource`

### List all available routes

`php artisan route:list`

### Migrate Database

Migrate
`php artisan migrate`

Drop Tables and Migrate again
`php artisan migrate:fresh`

### Create Seed

Create Seed
`php artisan make:seeder TaskTableSeeder`

Seed database (existing data is NOT deleted)
`php artisan db:seed`

Seed database and re-run migrations
`php artisan migrate:refresh --seed`
