## Getting started with Laravel

We are going to be using Laravel in future blog posts, that is why I thought it necessary to teach my audience how to use Laravel. Keep in mind that I use Laravel mostly for api building, so that's what we will focus on but Laravel can be used for many other things. 

If you really want to get started with Laravel, I would recommend you read the full documentation [here](https://laravel.com/docs)

## What is PHP

PHP is a general-purpose scripting language geared toward web development.

What this means is that PHP can be used to create server-side applications easily and efficiently. PHP has gotten a lot of flack over the years but it holds up and it is by far my best backend language despite how much I love Python.

## What is Laravel

Laravel is a free and open-source PHP web framework, created by Taylor Otwell and intended for the development of web applications following the model–view–controller (MVC) architectural pattern and based on Symfony.

Laravel makes API building very easy and straight forward. A lot of heavy lifting has already been taken care of. I believe it is the most starred framework on GitHub, but I'm not sure.

## Installations

Create a folder  and open it in vscode. In your terminal paste the following code :- `composer create-project laravel/laravel .`

This should install Laravel in your created folder. It will look something like this:

![laravel-dir-thumb.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1659773750986/ukVSuf80c.png align="left")

It may seem like a lot. Don't be over whelmed. You'll get used to it as you use Laravel. 

## Setting up

In your `.env` file, adjust the `APP_NAME` variable. Also edit the DB configurations to reflect that of your database.

```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=first_laravel
DB_USERNAME=joshy
DB_PASSWORD=mypassword
```

## Generating Migrations

Migrations are like version control for your database, allowing your team to define and share the application's database schema definition. If you have ever had to tell a teammate to manually add a column to their local database schema after pulling in your changes from source control, you've faced the problem that database migrations solve. ~ Laravel Docs.

`php artisan make:migration create_todos_table`

This will generate a migration file in your database/migrations folder. You will notice the following in that file:

```php
<?php

use Illuminate\Database\Migrations\Migration;
use Illuminate\Database\Schema\Blueprint;
use Illuminate\Support\Facades\Schema;

return new class extends Migration
{
    /**
     * Run the migrations.
     *
     * @return void
     */
    public function up()
    {
        Schema::create('todos', function (Blueprint $table) {
            $table->id();
            $table->string('name');
            $table->string('desc');
            $table->string('status');
            $table->timestamps();
        });
    }

    /**
     * Reverse the migrations.
     *
     * @return void
     */
    public function down()
    {
        Schema::dropIfExists('todos');
    }
};

```

Run `php artisan migrate`. This would create the tables of all the migrations listed in the migrations folder. 

Notes :-

- You can rollback migrations ( remove the last table), using the `php artisan migrate:rollback` command.
- You can check the status of your database using the `php artisan migrate:status` command. 
- You can rollback all migrations using the `php artisan migrate:reset` command.
- You can rollback all migrations and migrate them again using the `php artisan migrate:refresh` command.
- The `php artisan migrate:fresh` commands will drop all tables and then remigrate them. 
- DO NOT MANIPULATE YOUR TABLES SCHEMA DIRECTLY. ONLY USE MIGRATIONS.

## Laravel Models

Laravel includes Eloquent, an object-relational mapper (ORM) that makes it enjoyable to interact with your database. When using Eloquent, each database table has a corresponding "Model" that is used to interact with that table. In addition to retrieving records from the database table, Eloquent models allow you to insert, update, and delete records from the table as well.

To generate a Laravel Model, run `php artisan make:model Todo`.  This will generate a model that controls the todos table we just created. Your model should look like this.

```php
<?php

namespace App\Models;

use Illuminate\Database\Eloquent\Factories\HasFactory;
use Illuminate\Database\Eloquent\Model;

class Todo extends Model
{
    use HasFactory;

    protected $table = "todos";
}

```

Yours wont have the following `protected $table = "todos";`. Please add it. 
This specifies the database table you want the model to handle. It is necessary.

If you want to find out more about Models, click [here](https://laravel.com/docs/9.x/eloquent)


## Laravel Controllers

Instead of defining all of your request handling logic as closures in your route files, you may wish to organize this behavior using "controller" classes. Controllers can group related request handling logic into a single class. For example, a UserController class might handle all incoming requests related to users, including showing, creating, updating, and deleting users. By default, controllers are stored in the app/Http/Controllers directory.

To generate a controller, run the following in your terminal :- `php artisan make:controller TodosController`

You define functions in controllers. These functions can correspond to routes, or they can just be protected functions.

```php
<?php
 
namespace App\Http\Controllers;
 
use App\Http\Controllers\Controller;
use App\Models\Todo;
 
class TodosController extends Controller
{
    /**
     * Show the profile for a given user.
     *
     * @param  int  $id
     * @return \Illuminate\View\View
     */
    public function all()
    {
        $todo = Todo::all();
        return $todo;
    }
}
```

Notice how the Controller uses the Todo Model. This will allow us to access all the data in the database using the Eloquent ORM. 

## Laravel Routes

In `routes/api.php` file, you can create api routes. 

Let's create one :-

```php
use App\Http\Controllers\TodosController;

Route::get('todos', [TodosController::class, 'all']);
```

Now when you visit the route localhost:8000/api/todos, it will return all the todos in the todos table. 

To create a new route, follow this syntax :->

```php
Route::http-method('route-name', [Controller::class, 'function-name']);
```

for example :

```php
Route::post('add-todo', [TodosController::class, 'add']);
```

## Conclusion

That's it, hope you enjoy. 