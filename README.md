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

Create Migrations

`php artisan make:migration 'create_user_role_table'`

### Create Seed

Create Seed

`php artisan make:seeder TaskTableSeeder`

Seed database (existing data is NOT deleted)

`php artisan db:seed`

Seed database and re-run migrations

`php artisan migrate:refresh --seed`

### Authentication

Scaffold authentication

`php artisan make:auth`

### Middleware

Create Middleware

`php artisan make:middleware CheckRole`

### Controller

Create controller with resources (CRUD)

`php artisan make:controller AdminController --resource`

## Create Laravel Command

1. Make a command

`php artisan make:command TestCommand`

2. Add the following to the `kernel.php` file:

```
 protected $commands = [

    //This is the line of code added, at the end, we the have class name of DeleteInActiveUsers.php inside app\console\commands
        Commands\CoinMarketCapOverview::class,
    ];

    /**
     * Define the application's command schedule.
     *
     * @param  \Illuminate\Console\Scheduling\Schedule  $schedule
     * @return void
     */
    protected function schedule(Schedule $schedule)
    {
       //insert name and signature of you command and define the time of excusion
        $schedule->command('TestCommand:deleteusers')
                 ->everyMinute();
    }
```
3. `php artisan list` should show the command

DONE.


