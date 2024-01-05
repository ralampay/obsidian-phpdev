To run the development server (defaults to port `8000`):

```sh
php artisan serve
```

Running in a different port:

```sh
php artisan serve --port 3000
```


## Adding a Route

Routes can be found under `routes` directory. Basic setup is to call a method 

### Static Pages

**Example:** Creating an `GET /about` page

First define a route under `routes/web.php`:

```php
Route::get('/about', function() {
	return view('pages/about')
});
```

Create a blade view under `resources/views/pages/about.blade.php`. The return view value will be relative to `resources/views`.