# Статьи
1.  [Отправка писем с вложениями на нативном PHP](https://habr.com/ru/post/444744/)
2.  [Псевдотип «callable»](https://habr.com/ru/post/259991/)
3.  [Полиморфизм](https://habr.com/ru/post/37610/)
4.  [Динамическое создание PDF-файлов](https://www.ibm.com/developerworks/ru/library/x-buildpdfphp/index.html)

# Фреймворки
1.  [Laravel](frameworks/laravel/README.md)
2.  [Symphony](frameworks/symphony/README.md)
3.  [RedBean](frameworks/redBean/README.md)
4.  [Slim3](frameworks/slim3/README.md)

# Обучение
1.  [Unit tests](https://laracasts.com/topics/phpunit)

# Фишки
1.  Чтобы зарегистрировать политику без модели, в `AuthServiceProvoder` нужна следующая запись:  
```php
['policy' => NamePolicy::class];
```
Но использование политики совсем без модели - не правильно.
