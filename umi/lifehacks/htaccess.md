В последнем релизе старый вариант изменения .htaccess для запуска php скриптов больше не работает. Для новой версии нужно указать таким образом:
```
<FilesMatch "(?i)(adminer|phpinfo)\.php">
  Allow from all
  Require all granted
  php_flag engine on
</FilesMatch>
```
В скобках через | можно перечислить названия разрешенных скриптов
