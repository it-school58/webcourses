# Работа с файлами и директориями


<!------------------------------------------------------------->
#### Сохранение файла .txt на сервере
<!------------------------------------------------------------->
```php
<?php
    $file_path = '../uploads/1.txt';
    $file_content = 'Содержимое файла';
    $file = fopen($file_path, 'w');
    fwrite($file, $file_content);
    fclose($file);
?>
```

<!------------------------------------------------------------->
#### Проверка существования файла
<!------------------------------------------------------------->
```php
<?php
    $file = '../uploads/1.jpg';
    if (file_exists($file)) {
        echo "существует";
    } else {
        echo "не существует";
    }
?>
```

<!------------------------------------------------------------->
#### Удаление файла если он есть
<!------------------------------------------------------------->
```php
<?php
    $file = '../uploads/1.jpg';
    if ( file_exists($file) ) {
        unlink($file);
    }
?>
```

<!------------------------------------------------------------->
#### Создание директории если ее нет
<!------------------------------------------------------------->
```php
<?php
    $dir = '../uploads/'; 
    if( ! is_dir( $dir ) ) mkdir( $dir, 0777 );
?>
```

<!------------------------------------------------------------->
#### Удаление директории с файлами и поддиректориями
<!------------------------------------------------------------->
```php
<?php
    $dir = '../uploads/'; 
    if( is_dir( $dir ) ) {
        if ($objs = glob($dir."/*")) {
            foreach($objs as $obj) {
                is_dir($obj) ? removeDirectory($obj) : unlink($obj);
            }
        }
        rmdir($dir);
    }
?>
```

### Проект
- [Проект](https://disk.yandex.ru/d/lqMjxh4fxJ-n8g)
