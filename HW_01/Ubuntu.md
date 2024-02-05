1. Произвести минимальную настройку (время, локаль, custom motd)

Просмотр текущих настроек
![изображение](https://github.com/tms-dos21-onl/dzmitry-kuzin/assets/157679153/c8c98015-21c4-4a53-bf6e-d5e6145b003f)


Установить часовой пояс:

timedatectl set-timezone Europe/Minsk

Установить время:

sudo timedatectl -- set-time "17:11:50"

Установить дату

sudo timedatectl -- set-time "2024-02-05"

custom motd

sudo nano /etc/motd

![изображение](https://github.com/tms-dos21-onl/dzmitry-kuzin/assets/157679153/d9c79aec-9aec-4375-9eb4-b04caaea0079)

2. Определить точную версию ядра.

![изображение](https://github.com/tms-dos21-onl/dzmitry-kuzin/assets/157679153/e4597cfe-e834-4761-8013-365c2c039b3a)

3. Вывести список модулей ядра и записать в файл
