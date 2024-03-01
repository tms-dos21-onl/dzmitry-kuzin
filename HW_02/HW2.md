1. Создать новый виртуальный жёсткий диск, присоеденить его к VM, создать раздел (partition) и инициализировать на нём файловую системую.

  - Добавил новый диск 10 Gb.
  
  ![изображение](https://github.com/tms-dos21-onl/dzmitry-kuzin/assets/157679153/39f79bd5-aee5-4652-ba9c-4b0ca532d2a2)

  - Разметил диск.

  ![изображение](https://github.com/tms-dos21-onl/dzmitry-kuzin/assets/157679153/e25a10f4-380b-4849-9ff2-aeb6de699b34)

  - Форматирование нового роздела.

    ![изображение](https://github.com/tms-dos21-onl/dzmitry-kuzin/assets/157679153/a5407375-d8f3-4888-adc0-03eb23416747)

2. Смонтировать директорию /mnt/home на только что созданный раздел.

  - Добавляем запись в /etc/fstab чтобы включить постоянное монтирование файловой системы.

  ![изображение](https://github.com/tms-dos21-onl/dzmitry-kuzin/assets/157679153/b2112d69-5838-4fe6-9aac-1d68a2338b4b)

  - Монтирую все файловые ситемы перечисленные в /etc/fstab
  
    sudo mount -a
  
   ![изображение](https://github.com/tms-dos21-onl/dzmitry-kuzin/assets/157679153/e2c068a3-a193-47fc-8e54-c5f913a018f7)

3. Создать нового пользователя penguin с home-директорией /mnt/home/penguin:

        kds@kds-virtual-machine:~$ sudo useradd penguin -m -d /mnt/home/penguin

ключ -m при создании пользователя задаем домашний каталог

ключ -d задаем базовый каталог для домашнего каталога

        penguin:x:1001:1001::/mnt/home/penguin:/bin/sh
    
4. Создать новую группу пользователей birds, перенести в нее пользователя penguin.

- Группа birds:

      kds@kds-virtual-machine:~$ sudo groupadd birds

- Добавляем пользователя в группу birds:

      kds@kds-virtual-machine:~$ sudo usermod -a -G birds penguin

      kds@kds-virtual-machine:~$ cat /etc/group | grep birds
      birds:x:1002:penguin


5. Cоздать директорию /var/wintering и выдать права на нее только группе birds.

  - Cоздать директорию /var/wintering:

        kds@kds-virtual-machine:~$ sudo mkdir /var/wintering

  - выдать права на нее только группе birds:

        kds@kds-virtual-machine:~$ sudo chgrp  birds /var/wintering/

        kds@kds-virtual-machine:~$ sudo chmod 070 /var/wintering/

        kds@kds-virtual-machine:~$ ls -la /var/ | grep wintering
        d---rwx---  2 root birds    4096 фев 25 21:50 wintering


6. Установить ntpd (или chrony) и разрешить пользователю penguin выполнять команду systemctl restart chronyd (нужны права sudo).

  - установка chrony:
  
        kds@kds-virtual-machine:~$ sudo apt install chrony

        kds@kds-virtual-machine:~$ systemctl status chrony
        chrony.service - chrony, an NTP client/server
        Loaded: loaded (/lib/systemd/system/chrony.service; enabled; vendor preset>
        Active: active (running) since Fri 2024-03-01 09:38:15 +03; 1h 2min ago
        Docs: man:chronyd(8)
        man:chronyc(1)
        man:chrony.conf(5)
        Process: 834 ExecStart=/usr/lib/systemd/scripts/chronyd-starter.sh $DAEMON_>
        Main PID: 861 (chronyd)
        Tasks: 2 (limit: 4554)
        Memory: 2.2M
        CPU: 228ms
        CGroup: /system.slice/chrony.service
        ├─861 /usr/sbin/chronyd -F 1
        └─862 /usr/sbin/chronyd -F 1


  - Разрешить пользователю penguin выполнять команду systemctl restart chronyd

  Добавляем пользователя в группу sudo:

        kds@kds-virtual-machine:~$ sudo usermod -aG sudo penguin

  Переходим на пользователя penguin:

        kds@kds-virtual-machine:~$ su - penguin
        Пароль:
        penguin@kds-virtual-machine:~$

  Выполняем systemctl restart chronyd:

        penguin@kds-virtual-machine:~$ sudo systemctl restart chrony

        


   
   


   
