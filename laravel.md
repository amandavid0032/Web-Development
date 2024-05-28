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
