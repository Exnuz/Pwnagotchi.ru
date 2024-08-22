---
description: 'Минимальная конфигурация выглядит так:'
---

# Минимальная настройка config.toml

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

```toml
#Блок кода ниже отвечает за плагин grid, отправляет данные 
main.plugins.grid.enabled = true
main.plugins.grid.report = true
main.plugins.grid.exclude = [
  "YourHomeNetworkHere"
]

```

```toml
#Блок кода отвечает за отображение информации на экране
ui.display.enabled = true
ui.display.type = "waveshare_3"
ui.display.color = "black"
```
