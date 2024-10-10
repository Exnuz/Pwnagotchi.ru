# Минимальная настройка config.toml

Ниже представлена конфигурация для запуска устройства по имени: "Pwnagotchi" с дисплеем Waveshare v3-v4, с включенным плагином "Grid" и с сетями добавленными в белый список.

```toml
main.name = "pwnagotchi"
main.lang = "en"

main.whitelist = [
  "EXAMPLE_NETWORK",
  "ANOTHER_EXAMPLE_NETWORK",
  "fo:od:ba:be:fo:od",
  "fo:od:ba"
]

main.plugins.grid.enabled = true
main.plugins.grid.report = true
main.plugins.grid.exclude = [
  "YourHomeNetworkHere"
]

ui.display.enabled = true
ui.display.type = "waveshare_3"
ui.display.color = "black"
```

Вам нужно создать этот конфигурационный файл в любом текстовом редакторе с названием `config.toml` и положить в `boot` раздел SD карты на который вы записали образ Pwnagotchi.

`boot` - это единственный раздел который должен быть виден с Вашего компьютера независимо от вашей операционной системы, так как это простой FAT32.

При первом запуске Pwnagotchi этот файл перенесется в `/etc/pwnagotchi/config.toml`\
В дальнейшем при правильной записи рабочего образа Вы больше не увидите  `config.toml`  \
в  `boot` разделе.

### Main

```toml
main.name = "pwnagotchi" #Имя вашего pwnagotchi
main.lang = "en" #Язык отображения на экране и web интерфейсе

#Ниже список "белых сетей" которые pwnagotchi не будет атаковать
main.whitelist = [
  "EXAMPLE_NETWORK",
  "ANOTHER_EXAMPLE_NETWORK",
  "fo:od:ba:be:fo:od",
  "fo:od:ba"
]
```

Все доступные языки и их написание для config.toml можете увидеть здесь: [ТЫК](https://github.com/evilsocket/pwnagotchi/tree/ef0f35da0a4c7708a0e99dc0f75a4182efe328a5/pwnagotchi/locale)

### Grid

Если Вы хотите, чтобы ваш Pwnagotchi учувствовал в общих рейтингах PwnGrid (PwnGrid похож на Pokémon Go, но для WiFi!), а так же чтобы отображался в региональной статистике, вы можете разрешить отправлять своему Pwnagotchi базовую информацию о сетях которых он поймал.

```toml
#Блок кода ниже отвечает за плагин grid, отправляет данные 
main.plugins.grid.enabled = true # Вклюбчение плагина
main.plugins.grid.report = true # Полное согласие на участие в рейтинге
#Белый список сетей которые не стоит отправлять в Grid

main.plugins.grid.exclude = [
  "YourHomeNetworkHere", # both ESSIDs and BSSIDs are supported
  "de:ad:be:ef:de:ad"    # both ESSIDs and BSSIDs are supported
]
```

**Никакие захваченные криптографические материалы вашего Pwnagotchi не отправляются на сервер PwnGrid;** ТОЛЬКО минимальная информация для регистрации Pwnagotchi в базе данных PwnGrid (см. выше) и подсчета того, сколько сетей он «захватил» на данный момент, а именно:

* Список сетей, которых собирал Pwnagotchi (состоящий из их `BSSID`и `ESSID`).

### Display

_В разных прошивках разная поддержка дисплеев._

Вам нужно учесть и выбрать экран который подходит Вам.\
Параметр который можно указать в качестве дисплея - Ссылка на сайт с кратким описанием

`waveshare_1` - ([ТЫК](https://www.waveshare.com/wiki/2.13inch\_e-Paper\_HAT\_Manual))\
`waveshare_2` -  ([ТЫК](https://www.waveshare.com/wiki/2.13inch\_e-Paper\_HAT\_Manual))\
`waveshare_3` - ([ТЫК](https://www.waveshare.com/wiki/2.13inch\_e-Paper\_HAT\_Manual))\
`waveshare_4` - ([ТЫК](https://www.waveshare.com/wiki/2.13inch\_e-Paper\_HAT\_Manual))\
`waveshare27inch` - ([ТЫК](https://www.waveshare.com/wiki/2.7inch\_e-Paper\_HAT\_Manual))\
`waveshare27inch_v2` - ([ТЫК](https://www.waveshare.com/wiki/2.7inch\_e-Paper\_HAT\_Manual))\
`waveshare154inch` - ([ТЫК](https://www.waveshare.com/wiki/1.54inch\_e-Paper\_Module\_\(B\)\_Manual))\
`inky` - ([ТЫК](https://shop.pimoroni.com/products/inky-phat?variant=12549254217811))\
`papirus` - ([ТЫК](https://thepihut.com/products/papirus-zero-epaper-eink-screen-phat-for-pi-zero))\
`oledhat` - ([ТЫК](https://www.waveshare.com/wiki/1.3inch\_OLED\_HAT))\
`dfrobot` - ([ТЫК](https://wiki.dfrobot.com/Raspberry\_Pi\_e-ink\_Display\_Module\_SKU%3A\_DFR0591))

Остальные поддерживаемые дисплеи: ([ТЫК](https://github.com/evilsocket/pwnagotchi/blob/master/pwnagotchi/ui/display.py))

В большинстве сборок начиная с первых версий ванильного Pwnagotchi используется 2.13inch e-ink экран от Waveshare ([ТЫК](https://www.waveshare.com/2.13inch-e-paper-hat.htm#none;)).

В разных  isoбражений Pwnagotchi может и не быть нужного вам дисплея, инструкция написана конкретно под 1.5.5, 1.5.5FIX, (Будущий образ)

Стоит упомянуть что в 1.5.5 нет поддержки дисплея выше waveshare\_2 но есть в 1.5.5FIX.

```toml
#Блок кода отвечает за отображение информации на экране
ui.display.enabled = true #Включение плагина, false в случае если вы не используете экран обязателен.
ui.display.type = "waveshare_3" #Тип экрана который вы используете
ui.display.color = "black" #Возможные варианты: красный/желтый/черный (черный используется для монохромных дисплеев)
ui.fps = 0.0 #Интервал обновления дисплея
```

На момент написания инструкции (вторая половина 2024  года), выпускается и остается самым распространенным дисплей `waveshare_4`, определяется версия по наклейке на задней стороне платы.

Для платы  `waveshare`  v3-v4 следует выставить параметр `waveshare_3.`

Вы можете настроить интервал обновления дисплея через: `ui.fps`\
Рекомендуется использовать низкую частоту обновления экрана, чтобы избежать сокращения срока службы вашего e-ink дисплея.

