# Open Source Software and Tools (Practical)

**Course Code:** 05010107DS06  
**Program:** BCA (Hons)  
**Semester:** 7th Semester  
**Academic Year:** 2025-26  
**University:** Parul University, Faculty of Computer Applications

## Practical 1: Install Laravel using Composer

### Aim
Install Composer and Laravel on a local machine.

### Duration
1 Lab Session (2 Hours)

### Tools
PHP 8+, Composer, Terminal / Command Prompt

### Theory
Laravel is a free, open-source PHP web framework designed for building modern web applications following the MVC (Model-View-Controller) architectural pattern. Composer is the dependency manager for PHP that Laravel uses to manage packages and libraries.

### Step-by-Step Instructions

#### Step 1: Install PHP

1. Download XAMPP from `https://www.apachefriends.org` and install it.
2. Open a terminal and verify PHP:

```bash
php -v
```

3. The output should show a PHP 8.x version.

#### Step 2: Install Composer

1. Visit `https://getcomposer.org/download/` and download the installer for your OS.
2. On Windows, run `Composer-Setup.exe` and ensure PHP is added to PATH.
3. On Linux/Mac:

```bash
curl -sS https://getcomposer.org/installer | php
sudo mv composer.phar /usr/local/bin/composer
```

4. Verify Composer:

```bash
composer --version
```

#### Step 3: Install Laravel Installer Globally

```bash
composer global require laravel/installer
```

Add the Composer global bin directory to PATH, then verify:

```bash
laravel --version
```

#### Step 4: Create a New Laravel Project

Navigate to the desired directory, for example XAMPP's `htdocs`:

```bash
cd C:\xampp\htdocs
```

Create the project:

```bash
laravel new myapp
```

Or:

```bash
composer create-project laravel/laravel myapp
```

Then:

```bash
cd myapp
```

#### Step 5: Start the Development Server

```bash
php artisan serve
```

Open `http://127.0.0.1:8000` in a browser.

### Expected Output
Laravel welcome page displayed at `http://127.0.0.1:8000`.

### Common Errors and Solutions

- **`composer` is not recognized:** Ensure Composer is added to the system PATH and restart the terminal.
- **PHP version conflict:** Ensure PHP 8.0 or higher is installed and selected in PATH.

### Viva Questions

1. What is Composer? How is it different from npm?
2. What is the role of the Artisan command in Laravel?
3. What PHP version does Laravel 10 require?
4. What does the `vendor` folder contain in a Laravel project?

---

## Practical 2: Create a New Laravel Project: Basic Laravel Authenticator

### Aim
Set up a Laravel project with built-in authentication including login, registration, and logout.

### Duration
1 Lab Session (2 Hours)

### Tools
Laravel, Composer, Breeze/UI Package, Browser

### Theory
Laravel provides multiple starter kits for authentication. Laravel Breeze is the simplest option and includes login, registration, email verification, and password reset. It uses Blade templates with Tailwind CSS.

### Step-by-Step Instructions

#### Step 1: Create a New Project

```bash
composer create-project laravel/laravel auth-demo
cd auth-demo
```

#### Step 2: Configure the Database

Open the `.env` file and set:

```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=auth_demo
DB_USERNAME=root
DB_PASSWORD=
```

Create the `auth_demo` database in phpMyAdmin using XAMPP.

#### Step 3: Install Laravel Breeze

```bash
composer require laravel/breeze --dev
php artisan breeze:install blade
npm install && npm run dev
```

#### Step 4: Run Migrations

```bash
php artisan migrate
```

This creates the `users` table and other default tables.

#### Step 5: Serve and Test

```bash
php artisan serve
```

Test:

- Register: `http://127.0.0.1:8000/register`
- Login: `http://127.0.0.1:8000/login`
- Logout: use the navigation bar.

### Expected Output
Working register, login, logout, and dashboard pages with Tailwind CSS styling.

### Viva Questions

1. What is Laravel Breeze? How is it different from Laravel Jetstream?
2. What does `php artisan migrate` do?
3. Where are the authentication routes defined in a Breeze project?
4. What is the purpose of the `.env` file?

---

## Practical 3: Create Routes for Different Pages (Home, About, Contact)

### Aim
Define and configure routes for multiple pages in Laravel.

### Duration
1 Lab Session

### Tools
Laravel, `routes/web.php`, Artisan

### Theory
In Laravel, routes are defined in `routes/web.php`. Routes map a URL to a controller method or a closure. Laravel supports GET, POST, PUT, DELETE and other HTTP methods.

### Step-by-Step Instructions

#### Step 1: Open `routes/web.php`

Navigate to your project and open `routes/web.php`.

#### Step 2: Define Routes

```php
<?php

use Illuminate\Support\Facades\Route;

Route::get('/', function () {
    return view('home');
})->name('home');

Route::get('/about', function () {
    return view('about');
})->name('about');

Route::get('/contact', function () {
    return view('contact');
})->name('contact');
```

#### Step 3: Create Blade View Files

Create these files inside `resources/views/`:

- `home.blade.php`
- `about.blade.php`
- `contact.blade.php`

#### Step 4: Add Content to Each View

Example `resources/views/home.blade.php`:

```html
<!DOCTYPE html>
<html>
<head><title>Home</title></head>
<body>
    <h1>Welcome to the Home Page</h1>
    <nav>
        <a href="{{ route('home') }}">Home</a> |
        <a href="{{ route('about') }}">About</a> |
        <a href="{{ route('contact') }}">Contact</a>
    </nav>
</body>
</html>
```

Repeat similarly for `about.blade.php` and `contact.blade.php` with appropriate content.

#### Step 5: Test the Routes

```bash
php artisan serve
```

Visit:

- `http://127.0.0.1:8000/` for Home
- `http://127.0.0.1:8000/about` for About
- `http://127.0.0.1:8000/contact` for Contact

#### Step 6: List All Routes

```bash
php artisan route:list
```

### Expected Output
Three separate pages are accessible via URL, each showing its respective content.

### Viva Questions

1. What is the difference between a named route and an anonymous route?
2. What HTTP methods does Laravel support in routes?
3. What is the purpose of `Route::group()`?

---

## Practical 4: Create Corresponding View Files for Each Route

### Aim
Create and link Blade view templates for each defined route using layouts.

### Duration
1 Lab Session

### Tools
Laravel Blade Engine, `resources/views/`

### Theory
Laravel uses the Blade templating engine. Blade allows template inheritance using `@extends` and `@section` directives, making it easy to create consistent layouts across pages.

### Step-by-Step Instructions

#### Step 1: Create a Master Layout

Create `resources/views/layouts/app.blade.php`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>@yield('title', 'My App')</title>
    <style>
        body { font-family: Arial; margin: 40px; background: #f5f5f5; }
        nav a { margin-right: 15px; text-decoration: none; color: #1F4E79; }
    </style>
</head>
<body>
    <nav>
        <a href="{{ route('home') }}">Home</a>
        <a href="{{ route('about') }}">About</a>
        <a href="{{ route('contact') }}">Contact</a>
    </nav>
    <hr>
    <div class="content">
        @yield('content')
    </div>
</body>
</html>
```

#### Step 2: Update Each View to Extend the Layout

`resources/views/home.blade.php`:

```blade
@extends('layouts.app')
@section('title', 'Home')
@section('content')
    <h1>Welcome to Home Page</h1>
    <p>This is the home page of our Laravel application.</p>
@endsection
```

`resources/views/about.blade.php`:

```blade
@extends('layouts.app')
@section('title', 'About Us')
@section('content')
    <h1>About Us</h1>
    <p>We are a team of passionate web developers.</p>
@endsection
```

`resources/views/contact.blade.php`:

```blade
@extends('layouts.app')
@section('title', 'Contact')
@section('content')
    <h1>Contact Us</h1>
    <p>Email us at: contact@example.com</p>
@endsection
```

#### Step 3: Test All Pages

```bash
php artisan serve
```

Visit each page URL and confirm that the consistent navigation layout appears on all pages.

### Expected Output
All pages share the same navigation bar and layout via the master template.

### Viva Questions

1. What are `@yield` and `@section` in Blade?
2. How does template inheritance work in Laravel Blade?
3. What is the difference between `@include` and `@extends`?

---

## Practical 5: Pass Data from Routes to Views

### Aim
Pass dynamic data from routes to Blade view files and display it.

### Duration
1 Lab Session

### Tools
Laravel `routes/web.php`, Blade Views

### Theory
Data can be passed from routes or controllers to views using the `compact()` function, the `with()` method, or by directly passing an associative array as the second argument of the `view()` function.

### Step-by-Step Instructions

#### Method 1: Pass Data Using an Array

In `routes/web.php`:

```php
Route::get('/profile', function () {
    $name = "John Doe";
    $age = 22;
    $skills = ['PHP', 'Laravel', 'MySQL'];

    return view('profile', [
        'name' => $name,
        'age' => $age,
        'skills' => $skills
    ]);
});
```

#### Method 2: Pass Data Using `compact()`

```php
Route::get('/profile', function () {
    $name = "John Doe";
    $age = 22;
    $skills = ['PHP', 'Laravel', 'MySQL'];

    return view('profile', compact('name', 'age', 'skills'));
});
```

#### Method 3: Pass Data Using `with()`

```php
Route::get('/profile', function () {
    return view('profile')
        ->with('name', 'John Doe')
        ->with('age', 22);
});
```

#### Step 2: Create the Profile View

Create `resources/views/profile.blade.php`:

```blade
@extends('layouts.app')
@section('title', 'Profile')
@section('content')
    <h2>Student Profile</h2>
    <p><strong>Name:</strong> {{ $name }}</p>
    <p><strong>Age:</strong> {{ $age }}</p>
    <h3>Skills:</h3>
    <ul>
        @foreach($skills as $skill)
            <li>{{ $skill }}</li>
        @endforeach
    </ul>
@endsection
```

#### Step 3: Test

```bash
php artisan serve
```

Visit `http://127.0.0.1:8000/profile` and verify that the name, age, and skills are displayed correctly.

### Expected Output
Profile page displaying dynamic data: name, age, and a list of skills.

### Viva Questions

1. What are the different ways to pass data from a route to a view?
2. What does the `{{ }}` syntax do in Blade? Is it safe from XSS?
3. What is the difference between `{{ }}` and `{!! !!}` in Blade?

---

## Practical 6: Create Migrations for Database Tables

### Aim
Create and run database migrations for users and posts tables in Laravel.

### Duration
1 Lab Session

### Tools
Laravel Artisan, MySQL (XAMPP), `.env` Configuration

### Theory
Migrations in Laravel are like version control for your database. They allow you to define database structure in PHP and run changes using Artisan commands. Each migration file contains an `up()` method to apply changes and a `down()` method to reverse them.

### Step-by-Step Instructions

#### Step 1: Configure Database Connection

Update `.env`:

```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=laravel_db
DB_USERNAME=root
DB_PASSWORD=
```

Start XAMPP and create the `laravel_db` database in phpMyAdmin.

#### Step 2: Create Posts Migration

```bash
php artisan make:migration create_posts_table
```

#### Step 3: Define the Posts Table Schema

Open the generated migration in `database/migrations/` and update `up()`:

```php
public function up(): void
{
    Schema::create('posts', function (Blueprint $table) {
        $table->id();
        $table->foreignId('user_id')->constrained()->onDelete('cascade');
        $table->string('title');
        $table->text('content');
        $table->string('status')->default('draft');
        $table->timestamps();
    });
}
```

Define `down()`:

```php
public function down(): void
{
    Schema::dropIfExists('posts');
}
```

#### Step 4: Run Migrations

```bash
php artisan migrate
```

This creates all tables, including the default `users` table.

#### Step 5: Verify in phpMyAdmin

1. Start Apache and MySQL in XAMPP.
2. Open `http://localhost/phpmyadmin`.
3. Open `laravel_db` and confirm tables such as `users`, `posts`, and `migrations` exist.

### Useful Artisan Commands

```bash
php artisan migrate:rollback   # Undo last batch of migrations
php artisan migrate:refresh    # Rollback all and re-migrate
php artisan migrate:status     # Show migration status
```

### Expected Output
Tables `users`, `posts`, and other migration-related tables are created in the MySQL database.

### Viva Questions

1. What is the purpose of a migration in Laravel?
2. What does `php artisan migrate:rollback` do?
3. What is the difference between `timestamps()` and `softDeletes()`?
4. How do you create a foreign key relationship in a migration?

---

## Practical 7: Perform CRUD Operations on Database Records

### Aim
Implement Create, Read, Update, Delete (CRUD) operations for a Posts module.

### Duration
2 Lab Sessions

### Tools
Laravel MVC, Eloquent ORM, Blade, MySQL

### Theory
CRUD operations are the four basic functions of persistent storage. Laravel uses Eloquent ORM to interact with the database using PHP models. A resourceful controller provides the CRUD methods automatically.

### Step-by-Step Instructions

#### Step 1: Create Post Model and Controller

```bash
php artisan make:model Post -mcr
```

This creates a Model (`Post.php`), Migration, and Resource Controller.

#### Step 2: Define Fillable Fields in Model

Open `app/Models/Post.php`:

```php
<?php

namespace App\Models;

use Illuminate\Database\Eloquent\Model;

class Post extends Model
{
    protected $fillable = ['title', 'content', 'status'];
}
```

#### Step 3: Define Resource Route

In `routes/web.php`:

```php
use App\Http\Controllers\PostController;

Route::resource('posts', PostController::class);
```

#### Step 4: Implement Controller Methods

Open `app/Http/Controllers/PostController.php`.

```php
// INDEX - List all posts
public function index()
{
    $posts = Post::latest()->get();
    return view('posts.index', compact('posts'));
}

// CREATE - Show form
public function create()
{
    return view('posts.create');
}

// STORE - Save to DB
public function store(Request $request)
{
    Post::create($request->validate([
        'title' => 'required|max:255',
        'content' => 'required',
    ]));

    return redirect()->route('posts.index')->with('success', 'Post created!');
}

// EDIT - Show edit form
public function edit(Post $post)
{
    return view('posts.edit', compact('post'));
}

// UPDATE - Save changes
public function update(Request $request, Post $post)
{
    $post->update($request->validate([
        'title' => 'required|max:255',
        'content' => 'required',
    ]));

    return redirect()->route('posts.index')->with('success', 'Post updated!');
}

// DESTROY - Delete
public function destroy(Post $post)
{
    $post->delete();
    return redirect()->route('posts.index')->with('success', 'Post deleted!');
}
```

#### Step 5: Create Blade Views

Create `resources/views/posts/` with:

- `index.blade.php` for listing posts with Edit and Delete buttons.
- `create.blade.php` for creating a new post.
- `edit.blade.php` for editing an existing post.

Sample `create.blade.php`:

```blade
@extends('layouts.app')
@section('content')
<h2>Create Post</h2>

<form method="POST" action="{{ route('posts.store') }}">
    @csrf
    <input type="text" name="title" placeholder="Title" required><br>
    <textarea name="content" placeholder="Content" required></textarea><br>
    <button type="submit">Save Post</button>
</form>
@endsection
```

#### Step 6: Test All CRUD Operations

1. Visit `http://127.0.0.1:8000/posts` to list posts.
2. Click Create New Post to add a record.
3. Click Edit to modify a record.
4. Click Delete to remove a record.

### Expected Output
A fully working CRUD interface for creating, viewing, editing, and deleting posts from the database.

### Viva Questions

1. What is Eloquent ORM? How is it different from raw SQL?
2. What does `Route::resource()` generate?
3. What is `@csrf` and why is it required in forms?
4. What is the difference between `save()` and `create()` in Eloquent?

---

## Practical 8: Create and Deploy Demo Web Application using Laravel

### Aim
Build and deploy a complete demo web application integrating PHP with Laravel.

### Duration
2 Lab Sessions

### Tools
Laravel, MySQL, XAMPP, PHP, Blade, Bootstrap (optional)

### Theory
This practical consolidates the previous Laravel practicals into a complete mini-project. It integrates routing, views, database migrations, authentication, and CRUD into a deployable application.

### Project: Student Task Manager

#### Step 1: Create New Project with Auth

```bash
composer create-project laravel/laravel task-manager
cd task-manager
composer require laravel/breeze --dev
php artisan breeze:install blade
npm install && npm run dev
```

#### Step 2: Create Tasks Migration and Model

```bash
php artisan make:model Task -mcr
```

Migration schema in `database/migrations/..._create_tasks_table.php`:

```php
Schema::create('tasks', function (Blueprint $table) {
    $table->id();
    $table->foreignId('user_id')->constrained()->onDelete('cascade');
    $table->string('title');
    $table->text('description')->nullable();
    $table->enum('priority', ['low', 'medium', 'high'])->default('medium');
    $table->boolean('completed')->default(false);
    $table->timestamps();
});
```

#### Step 3: Set Fillable Fields and Relationships

`Task.php`:

```php
protected $fillable = ['title', 'description', 'priority', 'completed'];
```

`User.php`:

```php
public function tasks()
{
    return $this->hasMany(Task::class);
}
```

#### Step 4: Add Auth-Protected Task Routes

```php
Route::middleware('auth')->group(function () {
    Route::resource('tasks', TaskController::class);
});
```

#### Step 5: Implement Task Controller

Ensure all controller methods use `auth()->user()->tasks()` to scope operations to the logged-in user.

#### Step 6: Run and Test

```bash
php artisan migrate
php artisan serve
```

Register an account, log in, and test task creation, editing, completion toggle, and deletion.

### Expected Output
A fully functional authenticated task management web application.

### Deployment on XAMPP

1. Copy the project folder to `xampp/htdocs/`.
2. Update `.env` for production settings and run:

```bash
php artisan config:cache
```

3. Access the application at:

`http://localhost/task-manager/public`

### Viva Questions

1. How does middleware protect routes in Laravel?
2. What is MVC and how does Laravel implement it?
3. What steps are needed to deploy a Laravel app on shared hosting?

---

## Practical 9: Install WordPress on a Local Server Using XAMPP/WAMP

### Aim
Download, install, and configure WordPress on a local server environment.

### Duration
1 Lab Session

### Tools
XAMPP or WAMP, WordPress, phpMyAdmin, Browser

### Theory
WordPress is an open-source Content Management System (CMS). It is built with PHP and MySQL. XAMPP provides a local Apache, PHP, and MySQL environment for running WordPress without an internet hosting plan. WAMP provides a similar environment for Windows.

### Step-by-Step Instructions

#### Step 1: Start XAMPP Services

1. Open the XAMPP Control Panel.
2. Start the Apache and MySQL modules.
3. Verify that both show `Running` status with green indicators.

#### Step 2: Create a Database

1. Open `http://localhost/phpmyadmin`.
2. Click the **Databases** tab.
3. Enter database name: `wordpress_db`.
4. Select collation: `utf8_general_ci`.
5. Click **Create**.

#### Step 3: Download WordPress

1. Visit `https://wordpress.org/download/`.
2. Download the latest WordPress `.zip` file.
3. Extract the ZIP file.
4. Copy the extracted `wordpress` folder to:

```text
C:\xampp\htdocs\
```

5. Rename the folder to `mysite` (optional).

#### Step 4: Run WordPress Installer

Open:

`http://localhost/mysite`

1. Select your language and click **Continue**.
2. On the next screen, click **Let's go!**.
3. Enter database details:

```text
Database Name: wordpress_db
Username: root
Password: 
Database Host: localhost
Table Prefix: wp_
```

For the XAMPP default setup, leave the database password blank.

4. Click **Submit**, then **Run the Installation**.

#### Step 5: Complete Installation

1. Fill in the Site Title.
2. Set the Admin Username.
3. Set the Admin Password.
4. Enter the Admin Email.
5. Click **Install WordPress**.
6. After installation, click **Log In**.
7. Log in with the admin credentials to access the WordPress Dashboard.

### Expected Output
WordPress Dashboard is accessible at:

`http://localhost/mysite/wp-admin`

### Viva Questions

1. What is a CMS? Give examples other than WordPress.
2. What database does WordPress use by default?
3. What is the significance of the `wp-config.php` file?
4. What is the difference between XAMPP and WAMP?
