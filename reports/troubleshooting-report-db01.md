# Troubleshooting Report - db01


## server details
- Hostname: db01
- OS: RedHat 9.3
- Kernel: 5.14.0-362.8.1.el9_3.x86_64

## uptime
```text
 09:18:20 up 3 days, 12:44,  1 user,  load average: 0.07, 0.04, 0.01

## Disk Usage
```text
Filesystem             Size  Used Avail Use% Mounted on
devtmpfs               4.0M     0  4.0M   0% /dev
tmpfs                  1.8G     0  1.8G   0% /dev/shm
tmpfs                  721M   73M  648M  11% /run
/dev/mapper/rhel-root  8.0G  4.4G  3.7G  55% /
/dev/sda1              960M  299M  662M  32% /boot
/dev/sr0               9.9G  9.9G     0 100% /mnt/rhel
tmpfs                  361M   36K  360M   1% /run/user/1004
```

## Memory Usage
```text
               total        used        free      shared  buff/cache   available
Mem:            3600         663        2525          72         712        2937
Swap:           1023           0        1023
```

## Failed Services
```text
  UNIT                                LOAD   ACTIVE SUB    DESCRIPTION
● systemd-coredump@26-38347-0.service loaded failed failed Process Core Dump (PID 38347/UID 0)
● systemd-coredump@27-38346-0.service loaded failed failed Process Core Dump (PID 38346/UID 0)

LOAD   = Reflects whether the unit definition was properly loaded.
ACTIVE = The high-level unit activation state, i.e. generalization of SUB.
SUB    = The low-level unit activation state, values depend on unit type.
2 loaded units listed.
```

## Recent Error Logs
```text
Jul 11 15:10:44 db01 systemd-coredump[49801]: Process 49757 (systemd-journal) of user 0 dumped core.
Jul 11 15:10:43 db01 systemd[1]: systemd-udevd.service: Watchdog timeout (limit 3min)!
Jul 11 15:10:43 db01 systemd[1]: systemd-journald.service: Watchdog timeout (limit 3min)!
Jul 11 15:10:43 db01 systemd-coredump[49801]: Process 49757 (systemd-journal) of user 0 dumped core.
Jul 11 15:10:44 db01 systemd-coredump[49807]: Process 49739 (systemd-udevd) of user 0 dumped core.
Jul 11 16:10:09 db01 systemd-coredump[49818]: Process 49808 (systemd-journal) of user 0 dumped core.
Jul 11 16:10:08 db01 systemd[1]: systemd-journald.service: Watchdog timeout (limit 3min)!
Jul 11 16:10:08 db01 systemd-coredump[49818]: Process 49808 (systemd-journal) of user 0 dumped core.
Jul 11 16:45:31 db01 systemd-coredump[49858]: Process 49820 (systemd-journal) of user 0 dumped core.
Jul 11 16:45:30 db01 systemd[1]: systemd-logind.service: Watchdog timeout (limit 3min)!
Jul 11 16:45:30 db01 systemd[1]: systemd-journald.service: Watchdog timeout (limit 3min)!
Jul 11 16:45:31 db01 systemd-coredump[49858]: Process 49820 (systemd-journal) of user 0 dumped core.
Jul 11 16:45:31 db01 systemd-coredump[49861]: Process 49733 (systemd-logind) of user 0 dumped core.
Jul 12 02:59:30 db01 systemd-coredump[53319]: Process 49862 (systemd-journal) of user 0 dumped core.
Jul 12 02:59:29 db01 systemd[1]: systemd-logind.service: Watchdog timeout (limit 3min)!
Jul 12 02:59:29 db01 systemd[1]: systemd-journald.service: Watchdog timeout (limit 3min)!
Jul 12 02:59:29 db01 systemd-coredump[53319]: Process 49862 (systemd-journal) of user 0 dumped core.
Jul 12 02:59:30 db01 systemd-coredump[53323]: Process 49869 (systemd-logind) of user 0 dumped core.
Jul 12 03:14:42 db01 systemd[1]: systemd-udevd.service: Watchdog timeout (limit 3min)!
Jul 12 03:14:42 db01 systemd-coredump[53375]: Process 49813 (systemd-udevd) of user 0 dumped core.
Jul 12 04:15:57 db01 systemd-coredump[53385]: Process 53325 (systemd-journal) of user 0 dumped core.
Jul 12 04:15:56 db01 systemd[1]: systemd-journald.service: Watchdog timeout (limit 3min)!
Jul 12 04:15:57 db01 systemd-coredump[53385]: Process 53325 (systemd-journal) of user 0 dumped core.
Jul 12 04:58:57 db01 systemd-coredump[53427]: Process 53386 (systemd-journal) of user 0 dumped core.
Jul 12 04:58:57 db01 systemd[1]: systemd-logind.service: Watchdog timeout (limit 3min)!
Jul 12 04:58:57 db01 systemd[1]: systemd-journald.service: Watchdog timeout (limit 3min)!
Jul 12 04:58:57 db01 systemd-coredump[53427]: Process 53386 (systemd-journal) of user 0 dumped core.
Jul 12 04:58:57 db01 systemd-coredump[53428]: Process 53349 (systemd-logind) of user 0 dumped core.
Jul 12 05:58:36 db01 systemd-coredump[53444]: Process 53429 (systemd-journal) of user 0 dumped core.
Jul 12 05:58:34 db01 systemd[1]: systemd-logind.service: Watchdog timeout (limit 3min)!
Jul 12 05:58:34 db01 systemd[1]: systemd-journald.service: Watchdog timeout (limit 3min)!
Jul 12 05:58:35 db01 systemd-coredump[53444]: Process 53429 (systemd-journal) of user 0 dumped core.
Jul 12 05:58:36 db01 systemd-coredump[53448]: Process 53439 (systemd-logind) of user 0 dumped core.
Jul 12 06:58:58 db01 systemd-coredump[53497]: Process 53447 (systemd-journal) of user 0 dumped core.
Jul 12 06:58:57 db01 systemd[1]: systemd-journald.service: Watchdog timeout (limit 3min)!
Jul 12 06:58:57 db01 systemd-coredump[53497]: Process 53447 (systemd-journal) of user 0 dumped core.
Jul 12 08:14:21 db01 systemd[1]: systemd-logind.service: Watchdog timeout (limit 3min)!
Jul 12 08:14:21 db01 systemd-coredump[53505]: Process 53498 (systemd-journal) of user 0 dumped core.
Jul 12 08:14:20 db01 systemd[1]: systemd-udevd.service: Watchdog timeout (limit 3min)!
Jul 12 08:14:20 db01 systemd[1]: systemd-journald.service: Watchdog timeout (limit 3min)!
Jul 12 08:14:20 db01 systemd-coredump[53505]: Process 53498 (systemd-journal) of user 0 dumped core.
Jul 12 08:14:21 db01 systemd-coredump[53508]: Process 53380 (systemd-udevd) of user 0 dumped core.
Jul 12 08:14:22 db01 systemd-coredump[53507]: Process 53476 (systemd-logind) of user 0 dumped core.
```

## Listening Ports
```text
Netid State  Recv-Q Send-Q Local Address:Port  Peer Address:PortProcess                                                                                                             
udp   UNCONN 0      0          127.0.0.1:323        0.0.0.0:*    users:(("chronyd",pid=742,fd=5)) ino:19727 sk:1 cgroup:/system.slice/chronyd.service <->                           
udp   UNCONN 0      0            0.0.0.0:45671      0.0.0.0:*    users:(("avahi-daemon",pid=729,fd=14)) uid:70 ino:19690 sk:2 cgroup:/system.slice/avahi-daemon.service <->         
udp   UNCONN 0      0            0.0.0.0:5353       0.0.0.0:*    users:(("avahi-daemon",pid=729,fd=12)) uid:70 ino:19688 sk:3 cgroup:/system.slice/avahi-daemon.service <->         
udp   UNCONN 0      0              [::1]:323           [::]:*    users:(("chronyd",pid=742,fd=6)) ino:19728 sk:4 cgroup:/system.slice/chronyd.service v6only:1 <->                  
udp   UNCONN 0      0               [::]:47908         [::]:*    users:(("avahi-daemon",pid=729,fd=15)) uid:70 ino:19691 sk:5 cgroup:/system.slice/avahi-daemon.service v6only:1 <->
udp   UNCONN 0      0               [::]:5353          [::]:*    users:(("avahi-daemon",pid=729,fd=13)) uid:70 ino:19689 sk:6 cgroup:/system.slice/avahi-daemon.service v6only:1 <->
tcp   LISTEN 0      128          0.0.0.0:22         0.0.0.0:*    users:(("sshd",pid=47860,fd=3)) ino:99038 sk:7 cgroup:/system.slice/sshd.service <->                               
tcp   LISTEN 0      4096       127.0.0.1:631        0.0.0.0:*    users:(("cupsd",pid=790,fd=7)) ino:20277 sk:8 cgroup:/system.slice/cups.service <->                                
tcp   LISTEN 0      128             [::]:22            [::]:*    users:(("sshd",pid=47860,fd=4)) ino:99047 sk:9 cgroup:/system.slice/sshd.service v6only:1 <->                      
tcp   LISTEN 0      4096           [::1]:631           [::]:*    users:(("cupsd",pid=790,fd=6)) ino:20276 sk:a cgroup:/system.slice/cups.service v6only:1 <->                       
tcp   LISTEN 0      80                 *:3306             *:*    users:(("mariadbd",pid=26643,fd=15)) uid:27 ino:49476 sk:b cgroup:/system.slice/mariadb.service v6only:0 <->       
```

## firewall status
```text
public (active)
  target: default
  icmp-block-inversion: no
  interfaces: enp0s3 enp0s8
  sources: 
  services: cockpit dhcpv6-client http ssh
  ports: 
  protocols: 
  forward: yes
  masquerade: no
  forward-ports: 
  source-ports: 
  icmp-blocks: 
  rich rules: 
	rule family="ipv4" source address="192.168.56.21" port port="3306" protocol="tcp" accept
