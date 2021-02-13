Если у вас много редиректов, то добавление простого макроса `redirectMap` может существенно почистить файл маршрутов.
```php
// RouteServiceProvider.php
Route::macro('redirectMap', function ($map, $status = 302) {
    foreach ($map as $old => $new) {
        Route::redirect($old, $new, $status);
    }
});

// web.php
Route::redirectMap([
    '/archives' => '/articles',
    '/twitter' => 'https://twitter.com',
]);
```
