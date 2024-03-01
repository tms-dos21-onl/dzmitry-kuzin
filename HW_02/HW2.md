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

3. Создать нового пользователя penguin с home-директорией /mnt/home/penguin.

  ![изображение](https://github.com/tms-dos21-onl/dzmitry-kuzin/assets/157679153/52875733-d1c0-4b4f-bcb6-a629434952be)

ключ -m при создании пользователя задаем домашний каталог

ключ -d задаем базовый каталог для домашнего каталога
  
    penguin:x:1001:1001::/mnt/home/penguin:/bin/sh
    
4. Создать новую группу пользователей birds, перенести в нее пользователя penguin.

    kds@kds-virtual-machine:~$ sudo groupadd birds

  Добавляем пользователя в группу birds
    
  ![изображение](https://github.com/tms-dos21-onl/dzmitry-kuzin/assets/157679153/d8c18d56-f167-4274-9e48-3b8ac5d893bb)

  ![изображение](https://github.com/tms-dos21-onl/dzmitry-kuzin/assets/157679153/bc528747-1c39-4397-98ca-81d578eab45f)

5. Cоздать директорию /var/wintering и выдать права на нее только группе birds.

  - Cоздать директорию /var/wintering

  ![изображение](https://github.com/tms-dos21-onl/dzmitry-kuzin/assets/157679153/75e92929-a405-4c5c-ab85-cdab354dde1f)

  - выдать права на нее только группе birds.

  ![изображение](https://github.com/tms-dos21-onl/dzmitry-kuzin/assets/157679153/3b977386-5db7-4ee0-8316-acb7497ec389)

  ![изображение](https://github.com/tms-dos21-onl/dzmitry-kuzin/assets/157679153/6023378b-d5d3-49bc-849e-eac80631e64d)

  ![изображение](https://github.com/tms-dos21-onl/dzmitry-kuzin/assets/157679153/78bbf2c6-2012-473b-a44c-d9aca7042f07)

6. Установить ntpd (или chrony) и разрешить пользователю penguin выполнять команду systemctl restart chronyd (нужны права sudo).

  - установка chrony
  
  ![изображение](https://github.com/tms-dos21-onl/dzmitry-kuzin/assets/157679153/9b152a20-0588-4511-828d-3d6aff84edae)

  ![изображение](https://github.com/tms-dos21-onl/dzmitry-kuzin/assets/157679153/95684339-774d-4f6f-8de3-1c5d4ffd9f6f)

  - Разрешить пользователю penguin выполнять команду systemctl restart chronyd

  


   
   


   
