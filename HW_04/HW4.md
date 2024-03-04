1. Отобразить все процессы в системе.

        kds@kds-virtual-machine:~$ ps -A

       PID TTY          TIME CMD
        1 ?        00:00:07 systemd
        2 ?        00:00:00 kthreadd
        3 ?        00:00:00 rcu_gp
        4 ?        00:00:00 rcu_par_gp
        5 ?        00:00:00 slub_flushwq
        6 ?        00:00:00 netns
       11 ?        00:00:00 mm_percpu_wq
       12 ?        00:00:00 rcu_tasks_kthread
       . . . . . . . . . . . .
       11715 ?        00:00:00 kworker/0:0-events
       11724 ?        00:00:00 kworker/0:1-events
       11739 pts/0    00:00:00 ps

   2. Запустить бесконечный процесс в фоновом режиме используя nohup.

      
