# Настройка окружения и среды разработки

## OpenServer

Набор, включающий себя все необходимые для запуска веб-приложений сервисы. 
Все компоненты интересующего нас стека (Apache, PHP, MySQL) в наличии. 

* [Страница загрузки](http://open-server.ru/download/)
* [Официальный сайт](http://open-server.ru/)

### Возможные проблемы

#### Конфликт со Skype
Скайп по-умолчанию занимает порты 80 и 443, тем самым не позволяя веб-серверу из комплекта OpenServer запуститься.
Нужно отключить использование этих портов в скайпе: Инструменты / Настройки / Дополнительно / Соединение. 
И перезапустить скайп.

## Консольный PHP
### Дистрибутив
Консольный PHP должен находиться отдельно от модуля PHP в составе OpenServer. Самый простой способ - скопировать его 
оттуда. Порядок действий: 

* Скопируйте *C:\OpenServer\modules\php\PHP-7* в *C:\Work\PHP-7*

В директории *C:\Work\PHP-7*:

* Скопируйте файл *php.ini-development* в *php.ini*

В созданном файле *php.ini* установите следующие значения:

* extension_dir = "./"
* error_reporting = E_ALL

### Переменные окружения
* PATH - в эту переменную окружения требуется добавить директорию с php.exe (C:\Work\PHP-7\)
* PHP_COMMAND - должна содержать полный путь к php.exe (C:\Work\PHP-7\php.exe)
* PHP_BIN - должна содержать полный путь к php.exe (C:\Work\PHP-7\php.exe)
* PHP_DIR - должна содержать полный путь к директории с php.exe со слешем на конце (C:\Work\PHP-7\)


## PuTTY

Знаменитый SSH клиент для Windows. 
Сам клиент нам пока не интересен, однако нам потребуются утилиты *plink.exe* и *pageant.exe*

* [Установщик](http://the.earth.li/~sgtatham/putty/latest/x86/putty-0.65-installer.exe)
* [Официальный сайт](http://www.chiark.greenend.org.uk/~sgtatham/putty/)

## GIT

Распределенная система контроля версий.

* [Установщик](https://git-scm.com/download/win)
* [Официальный сайт](https://git-scm.com/)

## PhpStorm

Лучшая (и единственная) среда разработки. Если вы фанат Sublime Text 2 или NetBeans, то нам с вами не по пути. 

* [Страница загрузки](https://www.jetbrains.com/phpstorm/download/)
* [Официальный сайт](https://www.jetbrains.com/phpstorm/)

## dbForge Studio for MySQL

Графический редактор для MySQL. Отличная замена повсеместно используемому phpMyAdmin.

* [Страница загрузки](https://www.devart.com/ru/dbforge/mysql/studio/download.html)
* [Официальный сайт](https://www.devart.com/ru/dbforge/mysql/studio/)

## Composer

Пакетный менеджер для PHP. Основа любого современного веб-приложения.

* [Страница загрузки](https://getcomposer.org/download/)
* [Официальный сайт](https://getcomposer.org/)
* [Основной репозиторий пакетов](https://packagist.org/)
