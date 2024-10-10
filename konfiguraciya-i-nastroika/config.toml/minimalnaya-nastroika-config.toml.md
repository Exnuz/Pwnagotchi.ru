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

При первом запуске Pwnagotchi этот файл перенесется в "`/etc/pwnagotchi/config.toml`"\
В дальнейшем при правильной записи рабочего образа Вы больше не увидите  `config.toml`  \
в  `boot` разделе.

Более подробное описание&#x20;

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

Если Вы хотите, чтобы ваш Pwnagotchi учувствовал в общих рейтингах PwnGrid (PwnGrid похож на Pokémon Go, но для WiFi!), а так же чтобы отображался в региональной статистике, вы можете разрешить отправлять своему Pwnagotchi базовую информацию о сетях которых он поймал.

**Никакие захваченные криптографические материалы вашего Pwnagotchi не отправляются на сервер PwnGrid;** ТОЛЬКО минимальная информация для регистрации Pwnagotchi в базе данных PwnGrid (см. выше) и подсчета того, сколько сетей он «захватил» на данный момент, а именно:

* Список сетей, которых собирал Pwnagotchi (состоящий из их `BSSID`и `ESSID`).

```toml
#Блок кода отвечает за отображение информации на экране
ui.display.enabled = true
ui.display.type = "waveshare_3"
ui.display.color = "black"
```
