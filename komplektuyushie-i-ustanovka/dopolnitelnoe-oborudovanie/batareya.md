---
description: >-
  Что нужно сделать чтобы перестать быть комнатным затворником и показать своему
  питомцу мир?
---

# Батарея

Если ты все-таки решил выйти на улицу, а заодно выгулять свой **Pwnagotch**i-то тебе понадобится его от чего-то запитать, и здесь у теб есть 2 путя:

1. Ты используешь слим (маленькую) версию Pwnagotchi вместе с **PowerBank**-ом подключенным в **Micro-USB** порт
2. Увеличиваем размер своего дружка прикрепляя к нему _Pi Sugar Battery_ или _UPS (UPS-lite)_

Держи табличку с некоторыми PowerBank-ами идругими источниками питания (Другие тоже подойдут):

<table><thead><tr><th>Производитель</th><th>Модель</th><th>Объем mAh</th><th width="137">Время работы</th><th data-hidden></th></tr></thead><tbody><tr><td>PiSugar</td><td>PowerPack L</td><td>1200</td><td>04:49:42</td><td></td></tr><tr><td>UPS-Lite</td><td>UPS-Lite V1.1</td><td>1000</td><td>03:10:00</td><td></td></tr><tr><td>Anker</td><td>AstroMini 79AN7913S</td><td>3200</td><td>10:18:00</td><td></td></tr><tr><td>Anker</td><td>PowerCore A1109</td><td>5000</td><td>05:--:--</td><td></td></tr><tr><td>Anker</td><td>PowerCore 20100</td><td>20000</td><td>19:44:--</td><td></td></tr><tr><td>Anker</td><td>Astro E7 A1210</td><td>25600</td><td>49:--:--</td><td></td></tr><tr><td>Anker</td><td>Astro E1 6700 A1211</td><td>6700</td><td>23:16:00</td><td></td></tr><tr><td>Xiaomi Mi</td><td>Mi PowerBank</td><td>10000</td><td>36:--:--</td><td></td></tr></tbody></table>



## Показ заряда батареи UPS-Lite с помощью плагина

**UPS-Lite** имеет в себе контроллер заряда батареи способны сообщать уровень заряда через **i2C** интерфейс, также он имеет в себет UART->USB адаптер, через который можно подключиться к Pwnagotchi через зарядный порт.

Для отображения заряда в процентах используйте плагин [UPS\_Lite](https://github.com/evilsocket/pwnagotchi/blob/master/pwnagotchi/plugins/default/ups\_lite.py). Не забудьте включить **i2C** интерфейс в _raspi-config_
