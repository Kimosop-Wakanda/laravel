#### Creating new project in Laravel
 Via Composer
```
composer create-project laravel/laravel your-project-name 4.2.*
```
 serving laravel
```
php artisan serve
```
or
```
php artisan serve --port=8080
```

##### Routing
```
Route::get('users', function()
{
    return 'Users!';
});
```
```
Route::get('users', 'UserController@getIndex');
```

##### Creating a view
```
<html>
    <body>
        <h1>Laravel Quickstart</h1>
 
        @yield('content')
    </body>
</html>
```

```
@extends('layout')
 
@section('content')
    Users!
@stop
```

### Creating a Migration

```php artisan migrate:make create_users_table
```

 Defining a Migation
 ```
 public function up()
{
    Schema::create('users', function($table)
    {
        $table->increments('id');
        $table->string('email')->unique();
        $table->string('name');
        $table->timestamps();
    });
}
 
public function down()
{
    Schema::drop('users');
}
 ```
##### Migrating tables
```
php artisan migrate
```
