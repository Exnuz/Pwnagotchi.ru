# SSH

Один из самых простых способов подключиться к вашему Pwnagotchi это использовать `mini-usb` кабель и саму Raspberry pi в качестве `RDNS` гаджета.

_Обратите внимание что кабели бывают разные, используйте проверенные кабели которые передают данные._

Нужно учесть что RPI0w и RPI02w имеют два mini-usb разьема:

* `Power port` - используется только для подачи питания
* `Data port` - используется для подачи питания и обмена данными с устройствами.

<figure><img src="../.gitbook/assets/uLdQYqF (1).png" alt=""><figcaption></figcaption></figure>



1. Начните с присоединения вашей настроенной SD карты к Rpi.
2. Присоедините `mini-usb` кабель к `Data` порту Rpi
3. Присоедините вторую сторону кабеля к ПК.

В случае если вы до этого момента ни разу не включали Pwnagotchi, вам придется подождать \~5 мин.\
Не прерывайте работу Pwnagotchi во время этого процесса, он может перезапуститься несколько раз.\
При первом запуске Pwnagotchi, будет расширена файловая система до объёмов вашей карты памяти.\
При его перезапуске (делает это автоматически) Pwnagotchi начнет генерацию RSA ключей.

Если во время этого процесса вы выключите Pwnagotchi то RSA ключ может быть поврежден, также может быть поврежден и сам образ на SD карте.

Если все сделали правильно то во время подключения Pwnagotchi к ПК вы должны услышать звук подключенного устройства и должно появиться новое сетевое устройство в диспетчере устройств RDNS... .



