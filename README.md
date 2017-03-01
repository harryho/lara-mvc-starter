# lara-mvc-starter
This is a simple, skeleton application using the Laravel 5 MVC architect.

## About Laravel

Laravel is a web application framework with expressive, elegant syntax. We believe development must be an enjoyable, creative experience to be truly fulfilling. Laravel attempts to take the pain out of development by easing common tasks used in the majority of web projects, such as:

- [Simple, fast routing engine](https://laravel.com/docs/routing).
- [Powerful dependency injection container](https://laravel.com/docs/container).
- Multiple back-ends for [session](https://laravel.com/docs/session) and [cache](https://laravel.com/docs/cache) storage.
- Expressive, intuitive [database ORM](https://laravel.com/docs/eloquent).
- Database agnostic [schema migrations](https://laravel.com/docs/migrations).
- [Robust background job processing](https://laravel.com/docs/queues).
- [Real-time event broadcasting](https://laravel.com/docs/broadcasting).


### install laravel global `composer global laravel/installer`

### Change `php.ini` config 
#### * enable the `mbs-string` extension inside `php.ini`. Change the `;extension=php_mbstring.dll` as follow.
```ini
extension=php_mbstring.dll
```

### Overview 

The starter is a simple blog site. It provide simple database CRUD sample, and ORM sample, e.g. One to many relationship between different blog and comments. 

### Getting started

#### * migrate database and seed dummy data

```bash
php artisan migrate -VVV 
php artisan db:seed
```
#### * Troubleshooting

**Fix the error of Specified key was too long**

```php
namespace App\Providers;

use Illuminate\Support\ServiceProvider;
use Illuminate\Support\Facades\Schema;

class AppServiceProvider extends ServiceProvider
{
    /**
     * Bootstrap any application services.
     *
     * @return void
     */
    public function boot()
    {
        //
        Schema::defaultStringLength(191);
    }

    /**
     * Register any application services.
     *
     * @return void
     */
    public function register()
    {
        //
    }
}
```

#### * Start app with php built-in server 
**Linux**
```bash
php -S 0.0.0.0:8080 -t public/ public/index.php
```
**Windows**
```bash
php -S 0.0.0.0:8080 -t public public/index.php
```

## License

The Laravel framework is open-sourced software licensed under the [MIT license](http://opensource.org/licenses/MIT).
