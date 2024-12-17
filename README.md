# OTUS.Lesson8. ZFS
Для работы нам понадобится роль ansible-zfs (https://github.com/mrlesmithjr/ansible-zfs)  
Скачать и добавить в директорию role нашего проекта

Тестовый стенд: 4CPU, 4Gb RAM, HDD1 40G, HDD2-9 512M, OS Debian12  
Структура разделов:  
pz@LVM:~$ lsblk 
NAME               MAJ:MIN RM  SIZE RO TYPE MOUNTPOINTS  
sda                  8:0    0   40G  0 disk   
├─sda1               8:1    0  487M  0 part /boot  
├─sda2               8:2    0    1K  0 part   
└─sda5               8:5    0 39.5G  0 part   
  ├─LVM--vg-root   254:0    0 38.5G  0 lvm  /  
  └─LVM--vg-swap_1 254:1    0  976M  0 lvm  [SWAP]  
sdb                  8:16   0  512M  0 disk   
sdc                  8:32   0  512M  0 disk   
sdd                  8:48   0  512M  0 disk   
sde                  8:64   0  512M  0 disk   
sdf                  8:80   0  512M  0 disk   
sdg                  8:96   0  512M  0 disk   
sdh                  8:112  0  512M  0 disk   
sdi                  8:128  0  512M  0 disk   

Задания:  
1) Определить алгоритм с наилучшим сжатием:  
Определить какие алгоритмы сжатия поддерживает zfs (gzip, zle, lzjb, lz4);  
создать 4 файловых системы на каждой применить свой алгоритм сжатия;  
для сжатия использовать либо текстовый файл, либо группу файлов.  
2) Определить настройки пула.  
С помощью команды zfs import собрать pool ZFS.  
Командами zfs определить настройки:  
- размер хранилища;      
- тип pool;  
- значение recordsize;  
- какое сжатие используется;  
- какая контрольная сумма используется.  
3) Работа со снапшотами:  
скопировать файл из удаленной директории;  
восстановить файл локально. zfs receive;  
найти зашифрованное сообщение в файле secret_message.  
