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
3. Whenever I update a table by adding a new field to the existing database table, I need to create a new migration file for the same table and then run it using create `php artisan make: migration add_fields_to_students_table --table=students`.then run the migrate file 

---

## 📘 Controller
![Screenshot (449)](https://github.com/user-attachments/assets/28fa409a-e3f2-413e-8cd8-901a5a987851)

---

## 📘 How to see the page and continue count
```php
 @php $Sno = ($data->currentPage() - 1) * $data->perPage() + 1; @endphp
            @forelse ($data as $user)
                <tr>
                    <td>{{ $Sno }}</td>
                    <td>{{ $user->f_name }} {{ $user->l_name }}</td>
                    <td>{{ $user->email }}</td>
                    <td>{{ $user->phone }}</td>
                    <td>{{ $user->gender }}</td>
                    <td>
                        <a href="{{ route('view.user', $user->uid) }}" class='btn btn-info'>View</a>
                        <button type='button' class='btn btn-danger'data-id='{{ $user->uid }}'>Delete</button>
                    </td>
                </tr>
                @php $Sno++ @endphp
            @empty
                <tr>
                    <td colspan="6">
                        <h2>No Records Found</h2>
                    </td>
                </tr>
            @endforelse
        </tbody>
    </table>
    <div class="mt-5">{{ $data->links() }}</div>
```

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
    }    // This function returns all the results from the table students  get method

```

**Most Important Point** ==> Why we use query Builder
1. IT protects Your Application From SQL Injection Attacks By using PDO Parameter Binding
2. IT works with all of Laravel's Supported Database systems such as Mysql, SQL lite, MangoDb


For the Feath Data, there are so many ways 

```php
Where('id',$id);

oderBy('Name','asc');
```

---

**Insert Query**
1. Important Point
**`@csrf`** is a return Token

```php
"_token":"LqKQb01ECKTY0KzLjvrbvnp81Dc0HgKUWq0uC7oW"
```
This is a critical point if this is not used it shows the page hasn't been found so use this if any insert query runs or on an update

---

## 📘 Query Builder With Pagination
![Screenshot (450)](https://github.com/user-attachments/assets/90a9dadb-1c7b-453e-b4a3-98cc49ff7dba)
  
**There are Three Methods**

1. **Paginate()**=>This is the most common method used in Laravel for using pagination
  `DB::table('users')->paginate();   //In Query this use in model 
  {{ $data->links() }}             //In Blade template`
```php
public static function getUsers()
    {
        $user = DB::table('user')->orderBy('uid')->Paginate(4);
        return $user;
    }
//Use this class if don't use it and give an error 
public function boot(): void
    {
        Paginator::useBootstrapFive();
        // Paginator::useBootstrapFour();

    }
```
![Screenshot (453)](https://github.com/user-attachments/assets/383445e9-876c-4c37-97d6-9feb09138a21)
![Screenshot (452)](https://github.com/user-attachments/assets/6980ec4d-aaa6-481a-b386-d0170addd626)

3. **simplePaginate()**=>Same method as paginate just one different see in the photo and its default value is `15` per page record 
```php

public static function getUsers()
    {
        $user = DB::table('user')->orderBy('uid')->simplePaginate(4);
        return $user;
    }
```
4. **CursorPaginate()**=>1.It is used in large data sets and is faster with both methods because it works on indexing. Indexing the database cashing  columns will make the table faster, but it is not the most used.
   
**DissAdvantage**1.use Server Resource most and it will affect on other Processing on speed for `example it uses ram and memory and create cashing`

2.No Numberig On the pagination 

## 📘 Validation in Laravel
Benefits of the validation hacker Don't Bypass The layer Meaning hacker Don't hake Easily
```php
 <spam class="text-danger">@error('gender'){{ $message }}@enderror</spam>  //See Error in the blade template
 public function addNewUser(Request $req)
    {
        $req->validate([
            'firstname' => 'required',
            'lastname' => 'required',
            'fathername' => 'required',
            'mothername' => 'required',
            'gender' => 'required',
            'email' => 'required|email',
            'password' => 'required|alpha_num|min:8',
            'confirm_password' => 'required|same:password',
            'role' => 'required | numeric',
            'street' => 'required',
            'additional_info' => 'required',
            'zip_code' => 'required |numeric',
            'place' => 'required',
            'country' => 'required',
            'code' => 'required | numeric',
            'phone_number' => 'required |numeric',
        ]);
        return $req->all();
    }
```

**Custon Validation**
![Screenshot (458)](https://github.com/user-attachments/assets/4231978c-0f1d-49f5-a4a1-d55190440c59)

**Pending This work**

---






