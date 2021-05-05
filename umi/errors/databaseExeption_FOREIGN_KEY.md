При удалении поддомена с документацией возникает ошибка databaseExeption FOREIGN KEY.

Для решения этой проблемы, необходимо открыть adminer/phpMyAdmin и выполнить SQL команду:
```sql
ALTER TABLE `cms3_mail_notifications`
DROP FOREIGN KEY `notification to domain`,
ADD FOREIGN KEY (`domain_id`) REFERENCES `cms3_domains` (`id`) ON DELETE CASCADE ON UPDATE CASCADE
```
Он изменит поведение записей связанных внешним ключом при удалении с RESTRICT на CASCADE.
