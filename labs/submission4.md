## 1 Задание
## Выводы команд
# 1.1/1
gorbu@Ksusha:/mnt/c/Users/gorbu$ systemd-analyze
Startup finished in 4.322s (userspace)
graphical.target reached after 4.263s in userspace.

gorbu@Ksusha:/mnt/c/Users/gorbu$ systemd-analyze blame
2.452s snapd.seeded.service
1.766s landscape-client.service
 885ms dev-sdd.device
 707ms snapd.service
 330ms systemd-resolved.service
 324ms systemd-udev-trigger.service
 248ms systemd-journald.service
 246ms keyboard-setup.service
2.452s snapd.seeded.service
1.766s landscape-client.service
 885ms dev-sdd.device
 707ms snapd.service
 330ms systemd-resolved.service
 324ms systemd-udev-trigger.service
 248ms systemd-journald.service
 246ms keyboard-setup.service
 239ms user@1000.service
 191ms systemd-udevd.service
 191ms dev-hugepages.mount
 190ms dev-mqueue.mount
 190ms sys-kernel-debug.mount
 189ms sys-kernel-tracing.mount
 185ms rsyslog.service
 182ms systemd-timesyncd.service
 172ms systemd-logind.service
 169ms kmod-static-nodes.service
 166ms modprobe@configfs.service
 153ms modprobe@dm_mod.service
 153ms modprobe@drm.service
 121ms modprobe@efi_pstore.service
 114ms modprobe@fuse.service
 113ms modprobe@loop.service
  99ms systemd-tmpfiles-setup.service
  90ms systemd-tmpfiles-clean.service
  87ms systemd-modules-load.service
  84ms e2scrub_reap.service
  84ms dbus.service
  79ms systemd-tmpfiles-setup-dev-early.service
  76ms ldconfig.service
  75ms systemd-journal-flush.service
  72ms systemd-sysctl.service
  65ms systemd-binfmt.service
  65ms systemd-sysusers.service
  62ms systemd-journal-catalog-update.service
  50ms systemd-remount-fs.service
  41ms user-runtime-dir@1000.service
  39ms systemd-update-utmp.service
  34ms systemd-update-done.service
2.452s snapd.seeded.service
1.766s landscape-client.service
 885ms dev-sdd.device
 707ms snapd.service
 330ms systemd-resolved.service
 324ms systemd-udev-trigger.service
 248ms systemd-journald.service
 246ms keyboard-setup.service
 239ms user@1000.service
 191ms systemd-udevd.service
 191ms dev-hugepages.mount
 190ms dev-mqueue.mount
 190ms sys-kernel-debug.mount
 189ms sys-kernel-tracing.mount
 185ms rsyslog.service
 182ms systemd-timesyncd.service
 172ms systemd-logind.service
 169ms kmod-static-nodes.service
 166ms modprobe@configfs.service
 153ms modprobe@dm_mod.service
 153ms modprobe@drm.service
 121ms modprobe@efi_pstore.service
 114ms modprobe@fuse.service
 113ms modprobe@loop.service
  99ms systemd-tmpfiles-setup.service
  90ms systemd-tmpfiles-clean.service
  87ms systemd-modules-load.service
  84ms e2scrub_reap.service
  84ms dbus.service
  79ms systemd-tmpfiles-setup-dev-early.service
  76ms ldconfig.service
  75ms systemd-journal-flush.service
  72ms systemd-sysctl.service
  65ms systemd-binfmt.service
  65ms systemd-sysusers.service
  62ms systemd-journal-catalog-update.service
  50ms systemd-remount-fs.service
  41ms user-runtime-dir@1000.service
  39ms systemd-update-utmp.service
  34ms systemd-update-done.service
  33ms snapd.socket
  32ms console-setup.service
  31ms systemd-user-sessions.service
  28ms systemd-tmpfiles-setup-dev.service
  25ms setvtrgb.service
  23ms sys-fs-fuse-connections.mount
  18ms sys-kernel-config.mount
  13ms systemd-update-utmp-runlevel.service


# 1.1/2
gorbu@Ksusha:/mnt/c/Users/gorbu$ uptime
 14:59:00 up 19 min,  1 user,  load average: 0.00, 0.00, 0.00


gorbu@Ksusha:/mnt/c/Users/gorbu$ w
 14:59:05 up 19 min,  1 user,  load average: 0.00, 0.00, 0.00
USER     TTY      FROM             LOGIN@   IDLE   JCPU   PCPU  WHAT
gorbu    pts/1    -                14:41   17:08   0.04s  0.03s -bash


# 1.2/1
gorbu@Ksusha:/mnt/c/Users/gorbu$ ps -eo pid,ppid,cmd,%mem,%cpu --sort=-%mem | head -n 6
    PID    PPID CMD                         %MEM %CPU
    239       1 /usr/bin/python3 /usr/share  0.2  0.0
     56       1 /usr/lib/systemd/systemd-jo  0.1  0.0
    130       1 /usr/lib/systemd/systemd-re  0.1  0.0
      1       0 /sbin/init                   0.1  0.2
    538       1 /usr/lib/systemd/systemd --  0.1  0.0


gorbu@Ksusha:/mnt/c/Users/gorbu$ ps -eo pid,ppid,cmd,%mem,%cpu --sort=-%cpu | head -n 6
    PID    PPID CMD                         %MEM %CPU
      1       0 /sbin/init                   0.1  0.2
     56       1 /usr/lib/systemd/systemd-jo  0.1  0.0
    115       1 /usr/lib/systemd/systemd-ud  0.0  0.0
    130       1 /usr/lib/systemd/systemd-re  0.1  0.0
    239       1 /usr/bin/python3 /usr/share  0.2  0.0


# 1.3/1
gorbu@Ksusha:/mnt/c/Users/gorbu$ systemctl list-dependencies
default.target
○ ├─display-manager.service
○ ├─systemd-update-utmp-runlevel.service
○ ├─wslg.service
● └─multi-user.target
○   ├─apport.service
●   ├─console-setup.service
●   ├─cron.service
●   ├─dbus.service
○   ├─dmesg.service
○   ├─e2scrub_reap.service
○   ├─landscape-client.service
○   ├─networkd-dispatcher.service
●   ├─rsyslog.service
○   ├─snapd.apparmor.service
○   ├─snapd.autoimport.service
○   ├─snapd.core-fixup.service
○   ├─snapd.recovery-chooser-trigger.service
●   ├─snapd.seeded.service
○   ├─snapd.service
●   ├─systemd-ask-password-wall.path
●   ├─systemd-logind.service
○   ├─systemd-update-utmp-runlevel.service
●   ├─systemd-user-sessions.service
○   ├─ua-reboot-cmds.service
○   ├─ubuntu-advantage.service
●   ├─unattended-upgrades.service
●   ├─wsl-pro.service
●   ├─basic.target
○   │ ├─tmp.mount
●   │ ├─paths.target
○   │ │ └─apport-autoreport.path
●   │ ├─slices.target
●   │ │ ├─-.slice
●   │ │ └─system.slice
●   │ ├─sockets.target
●   │ │ ├─apport-forward.socket
●   │ │ ├─dbus.socket
●   │ │ ├─snapd.socket
●   │ │ ├─systemd-initctl.socket
●   │ │ ├─systemd-journald-dev-log.socket
●   │ │ ├─systemd-journald.socket
○   │ │ ├─systemd-pcrextend.socket
●   │ │ ├─systemd-sysext.socket
●   │ │ ├─systemd-udevd-control.socket
●   │ │ ├─systemd-udevd-kernel.socket
●   │ │ └─uuidd.socket
●   │ ├─sysinit.target
○   │ │ ├─apparmor.service
●   │ │ ├─dev-hugepages.mount
●   │ │ ├─dev-mqueue.mount
●   │ │ ├─keyboard-setup.service
●   │ │ ├─kmod-static-nodes.service
●   │ │ ├─ldconfig.service
○   │ │ ├─proc-sys-fs-binfmt_misc.automount
●   │ │ ├─setvtrgb.service
●   │ │ ├─sys-fs-fuse-connections.mount
●   │ │ ├─sys-kernel-config.mount
●   │ │ ├─sys-kernel-debug.mount
●   │ │ ├─sys-kernel-tracing.mount
●   │ │ ├─systemd-ask-password-console.path
●   │ │ ├─systemd-binfmt.service
○   │ │ ├─systemd-firstboot.service
○   │ │ ├─systemd-hwdb-update.service
●   │ │ ├─systemd-journal-catalog-update.service
●   │ │ ├─systemd-journal-flush.service
●   │ │ ├─systemd-journald.service
○   │ │ ├─systemd-machine-id-commit.service
●   │ │ ├─systemd-modules-load.service
○   │ │ ├─systemd-pcrmachine.service
○   │ │ ├─systemd-pcrphase-sysinit.service
○   │ │ ├─systemd-pcrphase.service
○   │ │ ├─systemd-pstore.service
○   │ │ ├─systemd-random-seed.service
○   │ │ ├─systemd-repart.service
●   │ │ ├─systemd-resolved.service
●   │ │ ├─systemd-sysctl.service
●   │ │ ├─systemd-sysusers.service
●   │ │ ├─systemd-timesyncd.service
●   │ │ ├─systemd-tmpfiles-setup-dev-early.service
●   │ │ ├─systemd-tmpfiles-setup-dev.service
●   │ │ ├─systemd-tmpfiles-setup.service
○   │ │ ├─systemd-tpm2-setup-early.service
○   │ │ ├─systemd-tpm2-setup.service
●   │ │ ├─systemd-udev-trigger.service
●   │ │ ├─systemd-udevd.service
●   │ │ ├─systemd-update-done.service
●   │ │ ├─systemd-update-utmp.service
●   │ │ ├─cryptsetup.target
●   │ │ ├─integritysetup.target
●   │ │ ├─local-fs.target
●   │ │ │ └─systemd-remount-fs.service
●   │ │ ├─swap.target
●   │ │ └─veritysetup.target
●   │ └─timers.target
○   │   ├─apport-autoreport.timer
●   │   ├─apt-daily-upgrade.timer
●   │   ├─apt-daily.timer
●   │   ├─dpkg-db-backup.timer
●   │   ├─e2scrub_all.timer
○   │   ├─fstrim.timer
●   │   ├─logrotate.timer
●   │   ├─man-db.timer
●   │   ├─motd-news.timer
○   │   ├─snapd.snap-repair.timer
●   │   ├─systemd-tmpfiles-clean.timer
○   │   └─ua-timer.timer
●   ├─getty.target
●   │ ├─console-getty.service
○   │ ├─getty-static.service
●   │ └─getty@tty1.service
●   └─remote-fs.target



gorbu@Ksusha:/mnt/c/Users/gorbu$ systemctl list-dependencies multi-user.target
multi-user.target
○ ├─apport.service
● ├─console-setup.service
● ├─cron.service
● ├─dbus.service
○ ├─dmesg.service
○ ├─e2scrub_reap.service
○ ├─landscape-client.service
○ ├─networkd-dispatcher.service
● ├─rsyslog.service
○ ├─snapd.apparmor.service
○ ├─snapd.autoimport.service
○ ├─snapd.core-fixup.service
○ ├─snapd.recovery-chooser-trigger.service
● ├─snapd.seeded.service
○ ├─snapd.service
● ├─systemd-ask-password-wall.path
● ├─systemd-logind.service
○ ├─systemd-update-utmp-runlevel.service
● ├─systemd-user-sessions.service
○ ├─ua-reboot-cmds.service
○ ├─ubuntu-advantage.service
● ├─unattended-upgrades.service
● ├─wsl-pro.service
● ├─basic.target
○ │ ├─tmp.mount
● │ ├─paths.target
○ │ │ └─apport-autoreport.path
● │ ├─slices.target
● │ │ ├─-.slice
● │ │ └─system.slice
● │ ├─sockets.target
● │ │ ├─apport-forward.socket
● │ │ ├─dbus.socket
● │ │ ├─snapd.socket
● │ │ ├─systemd-initctl.socket
● │ │ ├─systemd-journald-dev-log.socket
● │ │ ├─systemd-journald.socket
○ │ │ ├─systemd-pcrextend.socket
● │ │ ├─systemd-sysext.socket
● │ │ ├─systemd-udevd-control.socket
● │ │ ├─systemd-udevd-kernel.socket
● │ │ └─uuidd.socket
● │ ├─sysinit.target
○ │ │ ├─apparmor.service
● │ │ ├─dev-hugepages.mount
● │ │ ├─dev-mqueue.mount
● │ │ ├─keyboard-setup.service
● │ │ ├─kmod-static-nodes.service
● │ │ ├─ldconfig.service
○ │ │ ├─proc-sys-fs-binfmt_misc.automount
● │ │ ├─setvtrgb.service
● │ │ ├─sys-fs-fuse-connections.mount
● │ │ ├─sys-kernel-config.mount
● │ │ ├─sys-kernel-debug.mount
● │ │ ├─sys-kernel-tracing.mount
● │ │ ├─systemd-ask-password-console.path
● │ │ ├─systemd-binfmt.service
○ │ │ ├─systemd-firstboot.service
○ │ │ ├─systemd-hwdb-update.service
● │ │ ├─systemd-journal-catalog-update.service
● │ │ ├─systemd-journal-flush.service
● │ │ ├─systemd-journald.service
○ │ │ ├─systemd-machine-id-commit.service
● │ │ ├─systemd-modules-load.service
○ │ │ ├─systemd-pcrmachine.service
○ │ │ ├─systemd-pcrphase-sysinit.service
○ │ │ ├─systemd-pcrphase.service
○ │ │ ├─systemd-pstore.service
○ │ │ ├─systemd-random-seed.service
○ │ │ ├─systemd-repart.service
● │ │ ├─systemd-resolved.service
● │ │ ├─systemd-sysctl.service
● │ │ ├─systemd-sysusers.service
● │ │ ├─systemd-timesyncd.service
● │ │ ├─systemd-tmpfiles-setup-dev-early.service
● │ │ ├─systemd-tmpfiles-setup-dev.service
● │ │ ├─systemd-tmpfiles-setup.service
○ │ │ ├─systemd-tpm2-setup-early.service
○ │ │ ├─systemd-tpm2-setup.service
● │ │ ├─systemd-udev-trigger.service
● │ │ ├─systemd-udevd.service
● │ │ ├─systemd-update-done.service
● │ │ ├─systemd-update-utmp.service
● │ │ ├─cryptsetup.target
● │ │ ├─integritysetup.target
● │ │ ├─local-fs.target
● │ │ │ └─systemd-remount-fs.service
● │ │ ├─swap.target
● │ │ └─veritysetup.target
● │ └─timers.target
○ │   ├─apport-autoreport.timer
● │   ├─apt-daily-upgrade.timer
● │   ├─apt-daily.timer
● │   ├─dpkg-db-backup.timer
● │   ├─e2scrub_all.timer
○ │   ├─fstrim.timer
● │   ├─logrotate.timer
● │   ├─man-db.timer
● │   ├─motd-news.timer
○ │   ├─snapd.snap-repair.timer
● │   ├─systemd-tmpfiles-clean.timer
○ │   └─ua-timer.timer
● ├─getty.target
● │ ├─console-getty.service
○ │ ├─getty-static.service
● │ └─getty@tty1.service
● └─remote-fs.target


# 1.4/1
gorbu@Ksusha:/mnt/c/Users/gorbu$ who -a
           system boot  2026-02-23 14:40
           run-level 5  2026-02-23 14:40
LOGIN      console      2026-02-23 14:40               214 id=cons
LOGIN      tty1         2026-02-23 14:40               230 id=tty1
gorbu    - pts/1        2026-02-23 14:41 00:18         565


gorbu@Ksusha:/mnt/c/Users/gorbu$ last -n 5
reboot   system boot  6.6.87.2-microso Mon Feb 23 14:40   still running

wtmp begins Mon Feb 23 14:40:12 2026


# 1.5/1
gorbu@Ksusha:/mnt/c/Users/gorbu$ free -h
               total        used        free      shared  buff/cache   available
Mem:           7.4Gi       504Mi       6.9Gi       3.5Mi       143Mi       6.9Gi
Swap:          2.0Gi          0B       2.0Gi


gorbu@Ksusha:/mnt/c/Users/gorbu$ cat /proc/meminfo | grep -e MemTotal -e SwapTotal -e MemAvailable
MemTotal:        7787728 kB
MemAvailable:    7270992 kB
SwapTotal:       2097152 kB


## Основные выводы по каждому разделу анализа

* 1.1 Анализ производительности загрузки

 1 Анализ времени загрузки системы:
systemd-analyze показал, что userspace загрузился за 4.322 секунды, graphical.target был достигнут за 4.263 секунды. 
systemd-analyze blame выявил самые долгие службы: snapd.seeded.service (2.452 с), landscape-client.service (1.766 с) и dev-sdd.device (885 мс). 
Вывод: система загружается очень быстро, основная задержка — от Snap и Ubuntu Pro.

 2 Проверка загрузки системы:
Команды uptime и w показали, что система работает 19 минут, 1 пользователь, load average 0.00 0.00 0.00. 
Вывод: система полностью свободна, никакой нагрузки.

* 1.2 Судебно-медицинская экспертиза

 1 Выявление ресурсоемких процессов:
Команда ps --sort=-%mem показала, что максимум памяти занимает PID 239 (/usr/bin/python3 /usr/share/...) — 0.2 %. 
Команда ps --sort=-%cpu показала, что максимум CPU занимает init (PID 1) — 0.2 %. 
Вывод: все процессы потребляют крайне мало ресурсов, система практически пустая.

* 1.3 Анализ зависимостей служб
 1 systemctl list-dependencies вывел дерево зависимостей default.target и multi-user.target. 
Активны стандартные службы Ubuntu в WSL: rsyslog, cron, dbus, snapd.seeded, unattended-upgrades и wslg.service. 
Вывод: зависимости корректные, лишних служб нет.

* 1.4 Анализ сессий и пользователей
 1 who -a показал только одного активного пользователя gorbu на pts/1. 
last -n 5 показал только текущий бут системы. 
Вывод: посторонних пользователей и старых сессий нет.

* 1.5 Анализ использования памяти
 1 free -h показал: всего 7.4 GiB RAM, используется 504 MiB (7 %), доступно 6.9 GiB. 
Swap 2.0 GiB, не используется вообще. 
Вывод: памяти более чем достаточно, система не испытывает никакого давления.

Общий вывод:
Операционная система Ubuntu 24.04 в WSL 2 находится в идеальном состоянии: быстрая загрузка, нулевая нагрузка, минимальное потребление ресурсов, только один пользователь.



## Какой процесс потребляет больше всего памяти?

Процесс PID 239 (/usr/bin/python3 /usr/share/...) потребляет больше всего памяти — 0.2 %.
Все остальные процессы потребляют 0.1 % и меньше.


## Закономерности использования ресурсов

- Система находится в состоянии полного простоя: load average стабильно 0.00 по всем трём интервалам (1, 5 и 15 минут).
- Потребление оперативной памяти крайне низкое — всего 504 MiB из 7.4 GiB (примерно 7 %). При этом доступно ещё 6.9 GiB.
- Swap-файл вообще не используется (0 B из 2 GiB).
- Общая картина типична для свежеустановленной Ubuntu в WSL 2 без запущенных приложений и дополнительных сервисов.

Всё это максимально логично, потому что я уставновила Ubuntu в WSL только сегодня





## 2 Задание

## Выводы команд
# 2.1/1
gorbu@Ksusha:/mnt/c/Users/gorbu/fdsfsdfds/DevOps-Intro$ traceroute github.com
traceroute to github.com (140.82.121.4), 30 hops max, 60 byte packets
 1  Ksusha.mshome.net (172.20.176.1)  0.592 ms  0.584 ms  0.579 ms
 2  * * *
 3  * * *
 4  * * *
 5  * * *
 6  * * *
 7  * * *
 8  * * *
 9  * * *
10  * * *
11  * * *
12  * * *
13  * * *
14  * * *
15  * * *
16  * * *
17  * * *
18  * * *
19  * * *
20  * * *
21  * * *
22  * * *
23  * * *
24  * * *
25  * * *
26  * * *
27  * * *
28  * * *
29  * * *
30  * * *


# 2.1/2
gorbu@Ksusha:/mnt/c/Users/gorbu/fdsfsdfds/DevOps-Intro$ dig github.com

; <<>> DiG 9.18.39-0ubuntu0.24.04.2-Ubuntu <<>> github.com
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 45604
;; flags: qr rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 1232
;; QUESTION SECTION:
;github.com.                    IN      A

;; ANSWER SECTION:
github.com.             30      IN      A       4.225.11.194

;; Query time: 56 msec
;; SERVER: 10.255.255.254#53(10.255.255.254) (UDP) 
;; WHEN: Tue Feb 24 15:48:11 MSK 2026
;; MSG SIZE  rcvd: 55


# 2.2/1
gorbu@Ksusha:/mnt/c/Users/gorbu/fdsfsdfds/DevOps-Intro$ sudo timeout 10 tcpdump -c 5 -i any 'port 53' -nn
tcpdump: data link type LINUX_SLL2
tcpdump: verbose output suppressed, use -v[v]... for full protocol decode
listening on any, link-type LINUX_SLL2 (Linux cooked v2), snapshot length 262144 bytes

0 packets captured
0 packets received by filter
0 packets dropped by kernel


# 2.3/1
gorbu@Ksusha:/mnt/c/Users/gorbu/fdsfsdfds/DevOps-Intro$ dig -x 8.8.4.4

; <<>> DiG 9.18.39-0ubuntu0.24.04.2-Ubuntu <<>> -x 8.8.4.4
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 8901
;; flags: qr rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 512
;; QUESTION SECTION:
;4.4.8.8.in-addr.arpa.          IN      PTR

;; ANSWER SECTION:
4.4.8.8.in-addr.arpa.   12985   IN      PTR     dns.google.

;; Query time: 52 msec
;; SERVER: 8.8.8.8#53(8.8.8.8) (UDP)
;; WHEN: Thu Feb 26 00:28:31 MSK 2026
;; MSG SIZE  rcvd: 73

gorbu@Ksusha:/mnt/c/Users/gorbu/fdsfsdfds/DevOps-Intro$ dig -x 1.1.2.2

; <<>> DiG 9.18.39-0ubuntu0.24.04.2-Ubuntu <<>> -x 1.1.2.2
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NXDOMAIN, id: 62798
;; flags: qr rd ra ad; QUERY: 1, ANSWER: 0, AUTHORITY: 1, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 512
;; QUESTION SECTION:
;2.2.1.1.in-addr.arpa.          IN      PTR

;; AUTHORITY SECTION:
1.in-addr.arpa.         1705    IN      SOA     ns.apnic.net. read-txt-record-of-zone-first-dns-admin.apnic.net. 23597 7200 1800 604800 3600     

;; Query time: 52 msec
;; SERVER: 8.8.8.8#53(8.8.8.8) (UDP)
;; WHEN: Thu Feb 26 00:28:41 MSK 2026
;; MSG SIZE  rcvd: 137


**Получены данные о сетевых путях.**

Команда traceroute github.com показала только первый хоп — Ksusha.mshome.net (172.20.176.1) со временем ответа около 0,58 мс. Все последующие хопы (с 2 по 30) отобразились как * * *. 
Это нормальное поведение в WSL 2 из-за сетевой виртуализации Hyper-V и NAT — промежуточные маршрутизаторы не отвечают на ICMP-пакеты, поэтому полный путь снаружи не виден.


**Анализ шаблонов запросов/ответов DNS.**

Команда dig github.com выполнила прямой запрос типа A. 
Ответ пришёл успешно (статус NOERROR): github.com разрешается в IP-адрес 4.225.11.194 с TTL 30 секунд. 
Запрос был отправлен на DNS-сервер 10.255.255.254 (внутренний DNS-прокси WSL 2), время ответа — 56 мс.


**Сравнение результатов обратного поиска.**

Команда dig -x 8.8.4.4 выполнила обратный PTR-запрос.
Результат — NOERROR, получена PTR-запись: 8.8.4.4 соответствует доменному имени dns.google.
Это корректно, так как данный IP принадлежит публичному DNS-серверу Google и имеет настроенную обратную запись.

Команда dig -x 1.1.2.2 также выполнила PTR-запрос.
Результат — NXDOMAIN (доменное имя не найдено).
В authority-секции возвращена SOA-запись зоны 1.in-addr.arpa от сервера APNIC.

Это ожидаемое поведение, поскольку не все IP-адреса имеют настроенную reverse-запись в DNS.


**Пример DNS-запроса из перехваченных пакетов**

Команда tcpdump была запущена успешно, однако во время 10-секундного захвата пакетов DNS-трафик отсутствовал, поэтому было зафиксировано 0 пакетов.

Это связано с тем, что в момент выполнения tcpdump не производились DNS-запросы.