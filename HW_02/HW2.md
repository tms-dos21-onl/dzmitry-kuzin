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
  
  результат
  
  ![изображение](https://github.com/tms-dos21-onl/dzmitry-kuzin/assets/157679153/508a17bf-8b82-4e8c-bccf-6606347e792e)


   
