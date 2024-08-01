## 📔 Laravel 

## 📘 what is laravel
Laravel is a popular open-source PHP web framework used for building modern, dynamic web applications. It follows the MVC (Model-View-Controller) architectural pattern, which promotes separation of concerns and enhances code organization, making development more efficient and maintainable.

---

## 📘 Folder Structure 
![Screenshot (385)](https://github.com/amandavid0032/Web-Development/assets/86879390/8f37d15d-47c6-4c78-87ca-5b7b7d2b5e4b)

---
## 📘 Routes
In Laravel, routes are used to map HTTP request URLs to controller actions or closures. Routes define the entry points of your application and determine how incoming requests should be handled. Laravel provides a convenient way to define routes using the routes/web.php and routes/api.php files, although you can create additional route files if needed.

**GET**
```php
// first route write in get method 
Route::get('/', function () {
    return view('welcome');
});

```
**VIEW**
```php
// in View method its take 2 parameter 1. name of view 2. name of controller
Route::view('/singup', 'login');
//you can also select any name of the route for example
Route::view('/hello', 'login');
```
```php
php artisan route:list  //this command give the list of all the route
php artisan route:list --except-vendor //this command give the route which we made 
```
**Group Routes**
```php

Route::prefix('page')->group(function(){
    Route::view('/singup', 'login');
    Route::view('/welcome', 'welcome');
    // Route::view('/singup', 'login');
});
//just know write page/signup its is common routes
```
**fallback**
```php

Route::fallback(function(){
return "<h1>page dont found</h1>";
}); //it return me page dont find if there is no page or routes
```
---
## 📘 What is Blade Template
Laravel Blade is a powerful templating engine provided with Laravel, a popular PHP framework. Blade allows you to use plain PHP code in your templates, and it also provides its own control structures, such as conditional statements and loops, which are internally mapped to their PHP counterparts.
![Screenshot (386)](https://github.com/amandavid0032/Web-Development/assets/86879390/633a3e35-8d96-4ef6-add3-ff03b1886b0f)

---
## 📘 Database Migration
Database migrations in Laravel provide a way to manage and version your database schema. They allow you to create, modify, and share database structures across different environments and among team members. Migrations are like version control for your database, ensuring that you can easily apply changes and rollback if necessary
`php artisan migrate`

**Important Point**
Remember the following:
1. When I create a table using migration, it automatically adds an `s` at the end of the table name. For example: user -> `users`, task -> `tasks`.
2. Never delete session files as it will result in an error.
3. Whenever I update a table by adding a new field to the existing database table, I need to create a new migration file for the same table and then run it using create `php artisan make:migration add_fields_to_students_table --table=students`.then run migrate file 

---

## 📘 Query Builder
There are 2 types of Query Builder

![Screenshot (425)](https://github.com/user-attachments/assets/d0d2f12c-0e6d-4313-bdac-77aace7bdf8d)


![Screenshot (426)](https://github.com/user-attachments/assets/7b899a28-e7c2-4732-a439-f327ee505251)

There is an Error if the inbuilt file Delete `session table does not exist like that 1401 `

```php
 public function showUser(){
        $user=DB::table('students')->get();
        return $user;
    }    // This function return all the results from the table students  get method

```

For the Feath Data, there are so many way 

```php
Where('id',$id);

oderBy('Name','asc');
```

---

**Insert Query**
1. Important Point
`@csrf` is a return Token

"_token":"LqKQb01ECKTY0KzLjvrbvnp81Dc0HgKUWq0uC7oW"

This is very important point if this is not used it shows the page hasn't been found so use this if any insert query run

---





