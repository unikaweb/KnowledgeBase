При обновлении UMI может возникнуть ошибка, что не существует таблица cms3_object_files.  
  
Для решения этой проблемы, необходимо открыть adminer/phpMyAdmin и выполнить SQL команду:
```sql
DROP TABLE IF EXISTS `cms3_object_files`;
CREATE TABLE `cms3_object_files` (
  `id` int(10) unsigned NOT NULL AUTO_INCREMENT,
  `obj_id` int(10) unsigned DEFAULT NULL,
  `field_id` int(10) unsigned DEFAULT NULL,
  `src` varchar(500) DEFAULT NULL,
  `title` varchar(255) DEFAULT NULL,
  `ord` int(10) unsigned DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `load field value` (`obj_id`,`field_id`),
  KEY `field_id` (`field_id`),
  KEY `obj_id` (`obj_id`),
  KEY `src` (`src`(255)),
  KEY `ord` (`ord`),
  CONSTRAINT `File object field content to field` FOREIGN KEY (`field_id`) REFERENCES `cms3_object_fields` (`id`) ON DELETE CASCADE,
  CONSTRAINT `File object field content to object` FOREIGN KEY (`obj_id`) REFERENCES `cms3_objects` (`id`) ON DELETE CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=utf8;
```
