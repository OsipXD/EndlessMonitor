EndlessMonitor
===========
Гибкий и бесплатный мониторинг для вашего сервера

Установка
-----
1. Настройте `config.php` 
2. Настройте ваш стиль (`/styles/ВЫБРАННЫЙ_СТИЛЬ/style.php`) 
3. Настройте список серверов в файле `serverlist.php`
4. Залейте папку с мониторингом на хостинг (Хостинг должен поддерживать сокеты!)
5. Дайте права на папке `status` 777 и файлу `cron.txt` 664

Использование
--------  
1. Формирование ссылки:
   Ссылка должна иметь вид: `http://САЙТ.ru/ПУТЬ_К_МОНИТОРИНГУ/check.php?ПАРАМЕТРЫ`						   
   Параметры могут быть такие: `server, name, text, icon`
    * `server` - сервер который надо мониторить (из `serverlist.php`)
    * `name` - имя картинки мониторинга
    * `text` - текст который будет написан рядом с количеством игроков
    * `icon` - иконка вначале мониторинга (предпочитаю не использовать)

   Параметры разделяются знаком `&`
   Обязателен к указанию только `server`, остальные параметры либо будут взяты 
   дефолтные значения, либо не будут учитываться.
   Если вы не указали параметр `name`, то по умолчанию будет взято имя `noname.png`
   
   Например: `server=endlessworlds&name=mymonitor&text=EwndlessWorlds` 
   
   В этом случае будет создана картинка мониторящая сервер endlessworlds, ip и порт которого указаны в файле `serverlist.php`, на картинке перед количесвом онлайна будет написано "EndlessWorlds" и файл с картинкой мониторинга будет называться `mymonitor.png`

   Пример ссылки: 
   `http://site.ru/monitoring_path/check.php?server=server&name=test&text=sandbox&icon=sword.png`

2. Есди вам нужно вывести мониторинг на сайт, то встраивать ссылку надо через фрейм. 
   Вот пример: 
    
	<iframe src="ТУТ_ССЫЛКА" frameborder="0" scrolling="no" width="100%" height="100%"></iframe>
	
   Так же можно добавлять в фрейм тэг `align`, если вам надо выравнять мониторинг.
   Например вот фрейм с тэегом выравнивания по левому краю:
    
	<iframe src="ТУТ_ССЫЛКА" frameborder="0" scrolling="no" width="100%" height="100%" align="left"></iframe>

Добавление своего сервера
---------
1. Откройте файл `serverlist.php`
2. Скопируйте настройки уже готового сервера и вставьте их после всех настроенных серверов, исправив название сервера, ip и порт сервера.
3. Теперь можно указать этот сервер в параметрах

Включение режима отладки
--------
1. Откройте файл `config.php`
2. Измените опцию `$debug` с false на true
3. После того как закончите отладку не забудьте вернуть опцию обратно в положение false. 

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
6. Ну а теперь можно поставить название вашего стиля в `config.php` и поделиться этим стилем на RuBukkit (хорошие стили будут добавляться в сборку).

----------
[EndlessWorlds](http://endlessworlds.ru/)(c) OsipXD

Тема на [RuBukkit.org](http://rubukkit.org/threads/%D0%93%D0%B8%D0%B1%D0%BA%D0%B8%D0%B9-%D0%BC%D0%BE%D0%BD%D0%B8%D1%82%D0%BE%D1%80%D0%B8%D0%BD%D0%B3-%D0%A1%D1%82%D0%B8%D0%BB%D0%B8-cron-alternate-free.30897/page-6)