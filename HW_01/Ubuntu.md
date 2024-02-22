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

lsmod

модули ядра згруженные в данный момент записать в file

lsmod > file 

4. Просмотреть информацию о процессоре и модулях оперативной памяти

sudo lscpu > file1

Опреативная память

sudo lshw -class memory > file2

5. Получить информацию о жестком диске

sudo fdisk -l > file3

6. Добавить в виртуальную машину второй сетевой интерфейс (вывести информацию о нем в виртуалках)

kds@kds-virtual-machine:~$ ifconfig
ens33: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 192.168.145.129  netmask 255.255.255.0  broadcast 192.168.145.255
        inet6 fe80::5ffd:15ec:5c9a:fd56  prefixlen 64  scopeid 0x20<link>
        ether 00:0c:29:b9:13:a0  txqueuelen 1000  (Ethernet)
        RX packets 804  bytes 507278 (507.2 KB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 542  bytes 100653 (100.6 KB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

ens37: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 192.168.145.130  netmask 255.255.255.0  broadcast 192.168.145.255
        inet6 fe80::37f:21ba:fc91:16d3  prefixlen 64  scopeid 0x20<link>
        ether 00:0c:29:b9:13:aa  txqueuelen 1000  (Ethernet)
        RX packets 163  bytes 32540 (32.5 KB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 123  bytes 18144 (18.1 KB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1000  (Локальная петля (Loopback))
        RX packets 178  bytes 16802 (16.8 KB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 178  bytes 16802 (16.8 KB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0


7. Узнать полную информацию об использованной и неиспользованной оперативной памяти

![изображение](https://github.com/tms-dos21-onl/dzmitry-kuzin/assets/157679153/a0af40aa-81b2-4512-aa89-42559c6bcce6)


