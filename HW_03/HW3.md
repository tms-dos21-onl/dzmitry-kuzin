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

  - Количество свободной оперативной памяти:

          kds@kds-virtual-machine:~$ vmstat -s | grep -i 'free memory' | awk '{print $1}'
          842648

  - текущая загрузка процессора:

          kds@kds-virtual-machine:~$ top -n1 | grep "Cpu(s)"| awk '{print $2}'
          2,9
  
  - текущие IP адреса:

          kds@kds-virtual-machine:~$ hostname -I
          192.168.145.129 192.168.145.130

  - Собираем скрипт:
          
          #!/bin/bash
          Free_menory=$(vmstat -s | grep -i 'free memory' | awk '{print $1}')
          echo "Память: $Free_menory Мб"
          cpu=$(top -n1 | grep "Cpu(s)"| awk '{print $2}')
          echo "ЦПУ: $cpu"
          ip_addresses=$(hostname -I)
          echo "IP адреса: $ip_addresses"


          kds@kds-virtual-machine:~$ bash sysinfo.sh
          Память: 841640 Мб
          ЦПУ: 0,0
          IP адреса: 192.168.145.129 192.168.145.130


          
