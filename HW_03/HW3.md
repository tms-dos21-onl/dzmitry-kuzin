1. Познакомиться с утилитой Midnight Commander, установить её на VM и узнать с помощью неё все папки верхнего уровня файловой системы.

  - Устанавливаем Midnight Commander:

        kds@kds-virtual-machine:~$ sudo apt install mc

  - Запуск:

![изображение](https://github.com/tms-dos21-onl/dzmitry-kuzin/assets/157679153/37aea4c3-e6dc-4bfe-90e1-1b8cdcb6a6b0)

2. Установить PowerShell на VM и проверить, что он работаёт путем выполнения каких-нибудь простейших команд.

  - Установка PowerShell через Snap пакет:

          kds@kds-virtual-machine:~$ sudo snap install powershell --classic

          powershell 7.4.1 от Microsoft PowerShell✓ установлен

  - Запуск, проверка:

          PS /home/kds> exit
          kds@kds-virtual-machine:~$ pwsh
          PowerShell 7.4.1
          PS /home/kds> pwd

          Path
          ----
          /home/kds

3. Создать простейший bash-скрипт sysinfo.sh, который собирает данные о:
