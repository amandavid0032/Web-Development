## 📔 Laravel 

## 📘 what is laravel
Laravel is a popular open-source PHP web framework used for building modern, dynamic web applications. It follows the MVC (Model-View-Controller) architectural pattern, which promotes the separation of concerns and enhances code organization, making development more efficient and maintainable.

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

**Custom Validation**
![Screenshot (458)](https://github.com/user-attachments/assets/4231978c-0f1d-49f5-a4a1-d55190440c59)

**Pending This work**

---

## 📘 Resource Controller 
Resource controller is the method which is used for creating curd operation most of the time because it will create functions like add, insert, update

`php artisan make: model user --controller --resource`
this command will create a model and controller at the same time and resource create a function example-->insert, show, delete;
![Screenshot (462)](https://github.com/user-attachments/assets/6c39f4aa-0ea1-465c-a3f0-af3de8423245)

in the image u can see how the resource controller will work in the route it can only be used in action with the name of the data that I want to pass on it 

## 📘 Eloquent ORM Query (ORM object )

![Screenshot (460)](https://github.com/user-attachments/assets/e6b6a3e0-528b-4b55-b595-0d14cc720210)

**Eloquent ORM Supported Database** 

1.MySQL

2.SQL Server 

3.SQLite 

4.PostgreSQL

**What is Eloquent**
so Eloquent is a way to connect or fetch the data from the database with straight commands and simple  because it syntax is easy 


**Read Data**
```php
use App\Models\user;

    public function index()
    {
        $user = user::all();
        return $user;
    }   //It will fetch the data from the users table
```

## 📘 Image & File Upload 
In Laravel there are 2 folders where images can be uploaded
![Screenshot (466)](https://github.com/user-attachments/assets/e7139818-d69c-4c7f-90cb-a519d4fb9226)
There are 2 differences in storing an image or file in a folder.
1. If an image is saved in the app folder, it cannot be read because it is a locked folder that only stores important information.
2. There is no need to give a name or anything of the image I mean name so the image method automatically converts the name of the image

**Method to store images**
![Screenshot (467)](https://github.com/user-attachments/assets/122a15c0-0c80-4041-8ce4-c3750395dc12)

**store Method**
```php
  $file=$req->file('image');
        $req->validate(['image' => 'required|mimes:jpeg,png,jpg,gif,svg|max:2048',
        ]);
       $path=$req->file('image')->store('image','public');
        return $path;
```
**storeAs Method**
```php
   $file=$req->file('image');
        $req->validate(['image' => 'required|mimes:jpeg,png,jpg,gif,svg|max:2048',
        ]);
        $filename=$file->getClientOriginalName();                      // This methoda store image as it real name
        $filename=time().'_'.$file->getClientOriginalName();           // This method adds the time of the image on what time it will add 
        $path=$file->storeAs('image',$filename,'public');
        return $path;
```
**Important Point**
Whenever we want to see the image first we need to connect the storage file because the image doesn't see then 

`php artisan storage:link`

Storage folder add in this when this command runs   

---
## 📘 Laravel Middleware 
**What is Middleware** 

Middleware is a type of filtering mechanism that sits between the HTTP request and the controller. It is used to perform various tasks before or after a request is processed by the application.

Middleware acts as a bridge between a request and a response and can modify or handle the request and a response a can modify or handle the request before passing it to next step in the application life cycle  

**Create middleware**


`php artisan make:middleware ValidUser`

**Type of Middleware**

1. Route Middleware
2. Middleware Groups
3. Global  Middleware

Add Middleware in the Route 

`Route::get('/user/{id}', [userController::class, 'singleUser'])->name('view.user')->middleware(validUser::class);`

## 📘 Laravel Store Session 

A session  is a way to store information (data) across multiple requests from a user. Sessions allow you to preserve data across page loads and between requests, making it possible to remember user information, like authentication credentials, preferences, shopping cart contents, etc., throughout a user's interaction with the application.
![Screenshot (474)](https://github.com/user-attachments/assets/e9a6a10b-e68c-46f8-a4a0-5795d4308a5b)
```php
 public function index()
    {

        if (session()->has('name')) {
            $value = session()->get('name');
            echo $value;
        } else {
            echo "name don't exist";
        }


        // $value =session()->all();
        // echo"<pre>";
        // print_r($value);
        // echo"</pre>";
        // $value = session('name');
        // echo $value;
    }

    public function storeSession(Request $request)
    {
        session([
            'name' => 'David',
            "class" => "B.tech"
        ]);
        // session()->put('class', 'B.tech');
        return redirect('/');
    }



    public function deleteSession()
    {
        session()->forget('name');
        return redirect('/');
    }
```

## 📘  Gates in Laravel
Gates in Laravel are a way to authorize actions based on specific conditions. They provide a simple mechanism to define who can perform certain actions in your application. Gates are typically used to protect routes or certain actions within controllers based on a user's roles, permissions, or any other conditions.

While Gates are usually used for authorization logic that doesn’t require multiple policies, they are similar in purpose to policies. Gates are often used when the authorization logic is simple and doesn't warrant creating a full-fledged policy class. 

**Example**
1. Admin can only access Admin Panel or Specific page
2. User must be a valid age or user name
3. Valid users can view and update The user profile and settings page
4. user can update or delete their own post
5. user can only update their own comments and admin can
6. only the admin can approve the post

**Where we can use Gate**
1. Route
2. Blade File
3. controller
4. Middleware

**Gate in Route**
Route/Web.php 

`Route::get('/dashborad',[userController::class,'dashborad'])->middleware('can:isAdmin');`

---

**Blade File With Gates**
```php
@if(Gate::allows(isAdmin))
<a href="/amin-panel">Admin Panle</a>
@endif
```

```php
@can('isAdmin')
<a href="/admn-panel">Admin Panel</a>
@endcan
```
---
**Controller With Gates**
```php
public function dashboard(){
if(Gate:allows('isAdmin')){
return redirect()->route('dashboard');
}else{
return redirect()->route('login');
}
}
```
---
**Middleware with Gates** 
```php
public function handle(Request $request closure $next){
if(Gate::denies('isAdmin')){

}
}
```
---

**Defining Gates**

Gates are typically defined within the `App\Providers\AuthServiceProvider` class, using the Gate facade. You can define gates by using the Gate::define method.


`use Illuminate\Support\Facades\Gate;`

```php
Gate::define('update-post', function ($user, $post) {
    return $user->id === $post->user_id;
});
```
---
## 📘 Laravel Send Email 

**Step 1**
```php
MAIL_MAILER=smtp
MAIL_HOST=smtp.gmail.com
MAIL_PORT=587
MAIL_USERNAME=your_username
MAIL_PASSWORD=your_password
MAIL_ENCRYPTION=tls
MAIL_FROM_ADDRESS=your_email@example.com
MAIL_FROM_NAME="${APP_NAME}"

``` 
**Step 2** =>  Create a Mailable Class 

`php artisan make:mail ExampleMail`  this Command create a folder in the `app Then Mail`

**Example of the file**=> in this file it create 4 method 
```php
namespace App\Mail;

use Illuminate\Bus\Queueable;
use Illuminate\Mail\Mailable;
use Illuminate\Queue\SerializesModels;

class ExampleMail extends Mailable
{
    use Queueable, SerializesModels;

    public $details;

    /**
     * Create a new message instance.
     */
    public function __construct($details)
    {
        $this->details = $details;
    }

    /**
     * Build the message.
     */
    public function build()
    {
        return $this->subject('Test Email')
                    ->view('emails.example');
    }
}

```
**Step 3**
```php
use App\Mail\ExampleMail;
use Illuminate\Support\Facades\Mail;

class MailController extends Controller
{
    public function sendEmail()
    {
        $details = [
            'title' => 'Mail from Laravel',
            'body' => 'This is a test email sent from Laravel.'
        ];

        Mail::to('recipient@example.com')->send(new ExampleMail($details));

        return "Email Sent";
    }
}


```



