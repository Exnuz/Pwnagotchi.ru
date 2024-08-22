---
description: >-
  Начальная настройка после записи образа начинается с приготовления config.toml
  файла. Самого главного конфигурационного файла для pwnagotchi:
---

# Начальная конфигурация (config.toml)

Сразу разберемся с его содержимым:

Минимальная конфигурация выглядит так:

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
ui.display.type = "waveshare_2"
ui.display.color = "black"

```

```toml
// Some code
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
// Some code
#Блок кода ниже отвечает за плагин grid, отправляет данные 
main.plugins.grid.enabled = true
main.plugins.grid.report = true
main.plugins.grid.exclude = [
  "YourHomeNetworkHere"
]

```

```toml
// Some code
ui.display.enabled = true
ui.display.type = "waveshare_2"
ui.display.color = "black"
```
