# Troubleshooting Report - web01


## server details
- Hostname: web01
- OS: RedHat 9.3
- Kernel: 5.14.0-362.8.1.el9_3.x86_64

## uptime
```text
 09:18:19 up 3 days, 12:53,  1 user,  load average: 0.15, 0.03, 0.01

## Disk Usage
```text
Filesystem             Size  Used Avail Use% Mounted on
devtmpfs               4.0M     0  4.0M   0% /dev
tmpfs                  1.8G     0  1.8G   0% /dev/shm
tmpfs                  721M   73M  648M  11% /run
/dev/mapper/rhel-root  8.0G  4.1G  3.9G  52% /
/dev/sda1              960M  299M  662M  32% /boot
/dev/sr0               9.9G  9.9G     0 100% /mnt/rhel
tmpfs                  361M   36K  360M   1% /run/user/1002
```

## Memory Usage
```text
               total        used        free      shared  buff/cache   available
Mem:            3600         567        2777          72         554        3032
Swap:           1023           0        1023
```

## Failed Services
```text
  UNIT LOAD ACTIVE SUB DESCRIPTION
0 loaded units listed.
```

## Recent Error Logs
```text
Jul 11 15:10:42 web01 systemd-coredump[52930]: Process 52884 (systemd-journal) of user 0 dumped core.
Jul 11 15:10:41 web01 systemd[1]: systemd-logind.service: Watchdog timeout (limit 3min)!
Jul 11 15:10:42 web01 systemd[1]: systemd-journald.service: Watchdog timeout (limit 3min)!
Jul 11 15:10:42 web01 systemd-coredump[52930]: Process 52884 (systemd-journal) of user 0 dumped core.
Jul 11 15:10:42 web01 systemd-coredump[52931]: Process 52876 (systemd-logind) of user 0 dumped core.
Jul 11 16:10:07 web01 systemd[1]: systemd-udevd.service: Watchdog timeout (limit 3min)!
Jul 11 16:10:08 web01 systemd-coredump[52946]: Process 52903 (systemd-udevd) of user 0 dumped core.
Jul 11 16:45:29 web01 systemd-coredump[52990]: Process 52932 (systemd-journal) of user 0 dumped core.
Jul 11 16:45:29 web01 systemd[1]: systemd-logind.service: Watchdog timeout (limit 3min)!
Jul 11 16:45:29 web01 systemd[1]: systemd-udevd.service: Watchdog timeout (limit 3min)!
Jul 11 16:45:29 web01 systemd[1]: systemd-journald.service: Watchdog timeout (limit 3min)!
Jul 11 16:45:29 web01 systemd-coredump[52990]: Process 52932 (systemd-journal) of user 0 dumped core.
Jul 11 16:45:29 web01 systemd-coredump[52992]: Process 52965 (systemd-udevd) of user 0 dumped core.
Jul 11 16:45:30 web01 systemd-coredump[52993]: Process 52940 (systemd-logind) of user 0 dumped core.
Jul 12 02:25:30 web01 systemd-coredump[56445]: Process 52994 (systemd-journal) of user 0 dumped core.
Jul 12 02:25:29 web01 systemd[1]: systemd-logind.service: Watchdog timeout (limit 3min)!
Jul 12 02:25:29 web01 systemd[1]: systemd-journald.service: Watchdog timeout (limit 3min)!
Jul 12 02:25:30 web01 systemd-coredump[56445]: Process 52994 (systemd-journal) of user 0 dumped core.
Jul 12 02:25:30 web01 systemd-coredump[56448]: Process 53008 (systemd-logind) of user 0 dumped core.
Jul 12 03:14:41 web01 systemd[1]: systemd-logind.service: Watchdog timeout (limit 3min)!
Jul 12 03:14:41 web01 systemd-coredump[56504]: Process 56447 (systemd-journal) of user 0 dumped core.
Jul 12 03:14:41 web01 systemd[1]: systemd-udevd.service: Watchdog timeout (limit 3min)!
Jul 12 03:14:41 web01 systemd[1]: systemd-journald.service: Watchdog timeout (limit 3min)!
Jul 12 03:14:41 web01 systemd-coredump[56504]: Process 56447 (systemd-journal) of user 0 dumped core.
Jul 12 03:14:41 web01 systemd-coredump[56502]: Process 56457 (systemd-logind) of user 0 dumped core.
Jul 12 03:14:41 web01 systemd-coredump[56503]: Process 53001 (systemd-udevd) of user 0 dumped core.
Jul 12 04:15:56 web01 kernel: watchdog: BUG: soft lockup - CPU#0 stuck for 3422s! [systemd-udevd:56513]
Jul 12 04:15:56 web01 systemd-coredump[56519]: Process 56505 (systemd-journal) of user 0 dumped core.
Jul 12 04:15:55 web01 systemd[1]: systemd-journald.service: Watchdog timeout (limit 3min)!
Jul 12 04:15:55 web01 systemd-coredump[56519]: Process 56505 (systemd-journal) of user 0 dumped core.
Jul 12 04:15:56 web01 systemd[1]: Failed to start Rule-based Manager for Device Events and Files.
Jul 12 04:58:56 web01 systemd-coredump[56564]: Process 56523 (systemd-journal) of user 0 dumped core.
Jul 12 04:58:55 web01 systemd[1]: systemd-journald.service: Watchdog timeout (limit 3min)!
Jul 12 04:58:56 web01 systemd-coredump[56564]: Process 56523 (systemd-journal) of user 0 dumped core.
Jul 12 05:58:34 web01 systemd-coredump[56570]: Process 56565 (systemd-journal) of user 0 dumped core.
Jul 12 05:58:33 web01 systemd[1]: systemd-logind.service: Watchdog timeout (limit 3min)!
Jul 12 05:58:33 web01 systemd[1]: systemd-journald.service: Watchdog timeout (limit 3min)!
Jul 12 05:58:34 web01 systemd-coredump[56570]: Process 56565 (systemd-journal) of user 0 dumped core.
Jul 12 05:58:35 web01 systemd-coredump[56572]: Process 56521 (systemd-logind) of user 0 dumped core.
Jul 12 06:58:56 web01 systemd-coredump[56621]: Process 56574 (systemd-journal) of user 0 dumped core.
Jul 12 06:58:56 web01 systemd[1]: systemd-journald.service: Watchdog timeout (limit 3min)!
Jul 12 06:58:56 web01 systemd-coredump[56621]: Process 56574 (systemd-journal) of user 0 dumped core.
Jul 12 08:14:19 web01 systemd-coredump[56629]: Process 56624 (systemd-journal) of user 0 dumped core.
Jul 12 08:14:18 web01 systemd[1]: systemd-udevd.service: Watchdog timeout (limit 3min)!
Jul 12 08:14:18 web01 systemd[1]: systemd-journald.service: Watchdog timeout (limit 3min)!
Jul 12 08:14:19 web01 systemd-coredump[56629]: Process 56624 (systemd-journal) of user 0 dumped core.
Jul 12 08:14:20 web01 systemd-coredump[56631]: Process 56540 (systemd-udevd) of user 0 dumped core.
```

## Listening Ports
```text
Netid State  Recv-Q Send-Q Local Address:Port  Peer Address:PortProcess                                                                                                                  
udp   UNCONN 0      0            0.0.0.0:5353       0.0.0.0:*    users:(("avahi-daemon",pid=728,fd=12)) uid:70 ino:19689 sk:1 cgroup:/system.slice/avahi-daemon.service <->              
udp   UNCONN 0      0          127.0.0.1:323        0.0.0.0:*    users:(("chronyd",pid=739,fd=5)) ino:19721 sk:2 cgroup:/system.slice/chronyd.service <->                                
udp   UNCONN 0      0            0.0.0.0:55724      0.0.0.0:*    users:(("avahi-daemon",pid=728,fd=14)) uid:70 ino:19691 sk:3 cgroup:/system.slice/avahi-daemon.service <->              
udp   UNCONN 0      0               [::]:5353          [::]:*    users:(("avahi-daemon",pid=728,fd=13)) uid:70 ino:19690 sk:4 cgroup:/system.slice/avahi-daemon.service v6only:1 <->     
udp   UNCONN 0      0               [::]:50575         [::]:*    users:(("avahi-daemon",pid=728,fd=15)) uid:70 ino:19692 sk:5 cgroup:/system.slice/avahi-daemon.service v6only:1 <->     
udp   UNCONN 0      0              [::1]:323           [::]:*    users:(("chronyd",pid=739,fd=6)) ino:19722 sk:6 cgroup:/system.slice/chronyd.service v6only:1 <->                       
tcp   LISTEN 0      4096       127.0.0.1:631        0.0.0.0:*    users:(("cupsd",pid=788,fd=7)) ino:20301 sk:7 cgroup:/system.slice/cups.service <->                                     
tcp   LISTEN 0      128          0.0.0.0:22         0.0.0.0:*    users:(("sshd",pid=51016,fd=3)) ino:108593 sk:8 cgroup:/system.slice/sshd.service <->                                   
tcp   LISTEN 0      511          0.0.0.0:80         0.0.0.0:*    users:(("nginx",pid=12537,fd=6),("nginx",pid=12532,fd=6)) ino:35524 sk:9 cgroup:/system.slice/nginx.service <->         
tcp   LISTEN 0      128             [::]:22            [::]:*    users:(("sshd",pid=51016,fd=4)) ino:108602 sk:a cgroup:/system.slice/sshd.service v6only:1 <->                          
tcp   LISTEN 0      511             [::]:80            [::]:*    users:(("nginx",pid=12537,fd=7),("nginx",pid=12532,fd=7)) ino:35525 sk:b cgroup:/system.slice/nginx.service v6only:1 <->
tcp   LISTEN 0      4096           [::1]:631           [::]:*    users:(("cupsd",pid=788,fd=6)) ino:20300 sk:c cgroup:/system.slice/cups.service v6only:1 <->                            
```

## firewall status
```text
public (active)
  target: default
  icmp-block-inversion: no
  interfaces: enp0s3 enp0s8
  sources: 
  services: cockpit dhcpv6-client ssh
  ports: 80/tcp 443/tcp
  protocols: 
  forward: yes
  masquerade: no
  forward-ports: 
  source-ports: 
  icmp-blocks: 
  rich rules: 
