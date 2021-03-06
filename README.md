Установка
-----
1. Настройте `config.php` 
2. Настройте ваш стиль (`/styles/выбранный_стиль/style.php`) 
3. Настройте список серверов в файле `serverlist.php`
4. Залейте папку с мониторингом на хостинг (Хостинг должен поддерживать сокеты!)
5. [Дайте права](http://wiki.iblink.ru/faq/chmod) 777 папке `status` (перед этим создав ее если ее нету)

Использование
--------  
1. Надо [дать задание cron'у](http://ru.wikipedia.org/wiki/Cron) которое будет иметь такой вид:
   
   `php -f /полный_путь_к_мониторингу/draw.php название_сервера`
   
   (название сервера вы должны были указать в `serverlist.php`)
   или такой вид:
   
   `/usr/local/bin/php -f /полный_путь_к_мониторингу/draw.php название_сервера`
   
   Полный путь к мониторингу можно узнать, включив режим отладки (debug)
2. В результате выполнения создастся картинка `/status/название_сервера.png`. 
   Просто вставьте ее в любое место где нужен мониторинг.

Включение режима отладки (debug)
--------
1. Формирование ссылки:

   Ссылка должна иметь вид: `http://САЙТ.ru/путь_к_мониторингу/draw.php?server=название_сервера&debug=true`                       
   Пример ссылки: 
   `http://site.ru/monitoring_path/draw.php?server=server1&debug=true`
2. Теперь вставляем эту ссылку в аддресную строку. Скрипт запустится в режиме отладки.
   
Добавление своего сервера
---------
1. Откройте файл `serverlist.php`
2. Скопируйте настройки уже готового сервера и вставьте их после всех настроенных серверов, исправив название сервера, ip и порт сервера.
3. Теперь можно указать этот сервер в параметрах

Установка стиля 
---------	
1. Архив cо стилем разархиаировать в папку `styles`
2. В папке со стилем настроить файл `style.php` под себя
3. В файле config.php выбрать только что установленный стиль
 
Добавление своего стиля
---------
1. В папке `styles` создайе папку с названем вашего стиля, его потом будете вводить в настройках.
2. В нее добавьте файлы `offline.png` и `full.png`, нарисованные вами
    * `offline.png` - Показывается при ошибках и оффлайне.
    * `full.png` - когда сервер полный (можно отключать).
3. Добавьте файл `online.png`, он должен быть в два раза длиннее чем предыдущие файлы и наполовину заполнен, а наполовину пуст, как это сделано, например, в стиле Default.
4. Добавьте файл шрифта с названием `font.ttf`
5. И последний штрих - настройка стиля. Для этого скопируйте  уже настроенный файл `syles.php` из готового стиля (например Default) и поместите в папку вашего стиля (естественно предварительно настроив его).
6. Ну а теперь можно поставить название вашего стиля в `config.php` и поделиться этим стилем на RuBukkit (хорошие стили будут считаться официальными).

----------
[EndlessWorlds](http://endlessworlds.ru/)(c) OsipXD

Тема на [RuBukkit.org](http://rubukkit.org/threads/%D0%93%D0%B8%D0%B1%D0%BA%D0%B8%D0%B9-%D0%BC%D0%BE%D0%BD%D0%B8%D1%82%D0%BE%D1%80%D0%B8%D0%BD%D0%B3-%D0%A1%D1%82%D0%B8%D0%BB%D0%B8-cron-alternate-free.30897/page-6)
