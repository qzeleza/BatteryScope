## Описание проекта

Данный проект служит для отслеживания заряда батареии на Macbook и выдачи системных уведомлений на экран при наступлении лимитов (20/80 - по умолчанию), а также уведомлений в указанный Telegram канал.
Проект написан на AppleScript и bash.

## Установка скрипта 

```
git clone https://github.com/qzeleza/BatteryScope.git
cd BatteryScope
echo "telegramToken=<Ваш telegram Token>" > ./telegram.conf
echo "telegramChatId=<Ваш telegram ChatId>" >> ./telegram.conf
./battscope.run on
```

Скрипт установит в автозагрузку AppleScript скрипт battscope.scpt при помощи com.samovar.batteryscope.plist. 

## Установка порогов срабатывания

./battscope.run min 20
./battscope.run max 80

Они меняются прямо в тексте скрипта ./battscope.run и считываются через battscope.scpt.

## Справка по командам:
```
Скрипт запускает сервис отслеживания состояния зарядки ноутбука.

Использование: ./battscope.run {load|start|unload|stop|restart|status}
Использование: ./battscope.run {update|update '30'}

Описание ключей:

load|start|on   - загружаем сервис в автозагрузку
unload|stop|off - выгружавем сервис из автозагрузки
restart         - перезапускаем сервис
status|log      - отображаем статус сервиса
update          - отображаем период опроса состояния батареи
update '30'     - устанавливаем период опроса батереи в сек.
min         	- отображаем минимальный порог сигнала, в %
min 20      	- устанавливаем минимальный порог сигнала, в 20%
max         	- отображаем максимальный порог сигнала, в %
max 80      	- устанавливаем максимальный порог сигнала, в 80%
```