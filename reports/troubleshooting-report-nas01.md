# Troubleshooting Report - nas01


## server details
- Hostname: nas01
- OS: RedHat 9.3
- Kernel: 5.14.0-362.8.1.el9_3.x86_64

## uptime
```text
 09:18:21 up 3 days, 12:42,  1 user,  load average: 0.08, 0.02, 0.01

## Disk Usage
```text
Filesystem             Size  Used Avail Use% Mounted on
devtmpfs               4.0M     0  4.0M   0% /dev
tmpfs                  1.8G     0  1.8G   0% /dev/shm
tmpfs                  721M   73M  648M  11% /run
/dev/mapper/rhel-root  8.0G  1.8G  6.2G  22% /
/dev/sda1              960M  258M  703M  27% /boot
/dev/sr0               9.9G  9.9G     0 100% /mnt/rhel
tmpfs                  361M     0  361M   0% /run/user/1002
```

## Memory Usage
```text
               total        used        free      shared  buff/cache   available
Mem:            3600         560        2802          72         533        3039
Swap:           1023           0        1023
```

## Failed Services
```text
  UNIT                                LOAD   ACTIVE SUB    DESCRIPTION
● systemd-coredump@10-32152-0.service loaded failed failed Process Core Dump (PID 32152/UID 0)
● systemd-coredump@25-33569-0.service loaded failed failed Process Core Dump (PID 33569/UID 0)
● systemd-coredump@26-33567-0.service loaded failed failed Process Core Dump (PID 33567/UID 0)
● systemd-coredump@73-48366-0.service loaded failed failed Process Core Dump (PID 48366/UID 0)
● systemd-coredump@74-48367-0.service loaded failed failed Process Core Dump (PID 48367/UID 0)

LOAD   = Reflects whether the unit definition was properly loaded.
ACTIVE = The high-level unit activation state, i.e. generalization of SUB.
SUB    = The low-level unit activation state, values depend on unit type.
5 loaded units listed.
```

## Recent Error Logs
```text
Jul 12 03:14:42 nas01 systemd[1]: systemd-logind.service: Watchdog timeout (limit 3min)!
Jul 12 03:14:42 nas01 systemd[1]: systemd-udevd.service: Watchdog timeout (limit 3min)!
Jul 12 03:14:42 nas01 systemd[1]: systemd-journald.service: Watchdog timeout (limit 3min)!
Jul 12 03:14:42 nas01 systemd-coredump[48368]: Process 48320 (systemd-journal) of user 0 dumped core.
Jul 12 04:15:58 nas01 kernel: rcu: INFO: rcu_preempt self-detected stall on CPU
Jul 12 04:15:58 nas01 kernel: rcu:         0-...!: (1 ticks this GP) idle=8324/1/0x4000000000000000 softirq=315227/315227 fqs=0
Jul 12 04:15:58 nas01 kernel: rcu: rcu_preempt kthread timer wakeup didn't happen for 1474398 jiffies! g455457 f0x0 RCU_GP_WAIT_FQS(5) ->state=0x402
Jul 12 04:15:58 nas01 kernel: rcu:         Possible timer handling issue on cpu=0 timer-softirq=2006217
Jul 12 04:15:58 nas01 kernel: rcu: rcu_preempt kthread starved for 1474401 jiffies! g455457 f0x0 RCU_GP_WAIT_FQS(5) ->state=0x402 ->cpu=0
Jul 12 04:15:58 nas01 kernel: rcu:         Unless rcu_preempt kthread gets sufficient CPU time, OOM is now expected behavior.
Jul 12 04:15:58 nas01 kernel: rcu: RCU grace-period kthread stack dump:
Jul 12 04:15:58 nas01 kernel: rcu: Stack dump where RCU GP kthread last ran:
Jul 12 04:15:58 nas01 kernel: rcu: INFO: rcu_preempt self-detected stall on CPU
Jul 12 04:15:58 nas01 kernel: rcu:         0-...!: (2 ticks this GP) idle=8324/1/0x4000000000000000 softirq=315227/315227 fqs=0
Jul 12 04:15:58 nas01 kernel: rcu: rcu_preempt kthread starved for 3673500 jiffies! g455457 f0x0 RCU_GP_WAIT_FQS(5) ->state=0x0 ->cpu=0
Jul 12 04:15:58 nas01 kernel: rcu:         Unless rcu_preempt kthread gets sufficient CPU time, OOM is now expected behavior.
Jul 12 04:15:58 nas01 kernel: rcu: RCU grace-period kthread stack dump:
Jul 12 04:15:58 nas01 kernel: rcu: Stack dump where RCU GP kthread last ran:
Jul 12 04:15:58 nas01 systemd-coredump[48377]: Process 48370 (systemd-journal) of user 0 dumped core.
Jul 12 04:15:57 nas01 systemd[1]: systemd-journald.service: Watchdog timeout (limit 3min)!
Jul 12 04:15:57 nas01 systemd-coredump[48377]: Process 48370 (systemd-journal) of user 0 dumped core.
Jul 12 04:58:57 nas01 systemd[1]: systemd-logind.service: Watchdog timeout (limit 3min)!
Jul 12 04:58:57 nas01 systemd-coredump[48429]: Process 48382 (systemd-journal) of user 0 dumped core.
Jul 12 04:58:57 nas01 systemd[1]: systemd-udevd.service: Watchdog timeout (limit 3min)!
Jul 12 04:58:57 nas01 systemd[1]: systemd-journald.service: Watchdog timeout (limit 3min)!
Jul 12 04:58:57 nas01 systemd-coredump[48429]: Process 48382 (systemd-journal) of user 0 dumped core.
Jul 12 04:58:58 nas01 systemd-coredump[48435]: Process 48384 (systemd-logind) of user 0 dumped core.
Jul 12 04:58:58 nas01 systemd-coredump[48434]: Process 48378 (systemd-udevd) of user 0 dumped core.
Jul 12 05:58:36 nas01 systemd[1]: systemd-logind.service: Watchdog timeout (limit 3min)!
Jul 12 05:58:36 nas01 systemd[1]: systemd-udevd.service: Watchdog timeout (limit 3min)!
Jul 12 05:58:36 nas01 systemd-coredump[48456]: Process 48433 (systemd-journal) of user 0 dumped core.
Jul 12 05:58:35 nas01 systemd[1]: systemd-journald.service: Watchdog timeout (limit 3min)!
Jul 12 05:58:35 nas01 systemd-coredump[48456]: Process 48433 (systemd-journal) of user 0 dumped core.
Jul 12 05:58:36 nas01 systemd-coredump[48460]: Process 48444 (systemd-udevd) of user 0 dumped core.
Jul 12 05:58:37 nas01 systemd-coredump[48461]: Process 48450 (systemd-logind) of user 0 dumped core.
Jul 12 06:58:58 nas01 systemd[1]: systemd-logind.service: Watchdog timeout (limit 3min)!
Jul 12 06:58:58 nas01 systemd[1]: systemd-udevd.service: Watchdog timeout (limit 3min)!
Jul 12 06:58:58 nas01 systemd-coredump[48515]: Process 48459 (systemd-journal) of user 0 dumped core.
Jul 12 06:58:57 nas01 systemd[1]: systemd-journald.service: Watchdog timeout (limit 3min)!
Jul 12 06:58:57 nas01 systemd-coredump[48515]: Process 48459 (systemd-journal) of user 0 dumped core.
Jul 12 06:58:58 nas01 systemd-coredump[48518]: Process 48490 (systemd-udevd) of user 0 dumped core.
Jul 12 06:58:58 nas01 systemd-coredump[48522]: Process 48502 (systemd-logind) of user 0 dumped core.
Jul 12 08:14:21 nas01 systemd-coredump[48540]: Process 48520 (systemd-journal) of user 0 dumped core.
Jul 12 08:14:20 nas01 systemd[1]: systemd-journald.service: Watchdog timeout (limit 3min)!
Jul 12 08:14:20 nas01 systemd-coredump[48540]: Process 48520 (systemd-journal) of user 0 dumped core.
Jul 12 08:33:09 nas01 systemd-coredump[48581]: Process 48542 (systemd-journal) of user 0 dumped core.
Jul 12 08:33:08 nas01 systemd[1]: systemd-udevd.service: Watchdog timeout (limit 3min)!
Jul 12 08:33:08 nas01 systemd[1]: systemd-journald.service: Watchdog timeout (limit 3min)!
Jul 12 08:33:08 nas01 systemd-coredump[48581]: Process 48542 (systemd-journal) of user 0 dumped core.
Jul 12 08:33:09 nas01 systemd-coredump[48584]: Process 48527 (systemd-udevd) of user 0 dumped core.
```

## Listening Ports
```text
Netid State  Recv-Q Send-Q Local Address:Port  Peer Address:PortProcess                                                                                                                     
udp   UNCONN 0      0            0.0.0.0:60641      0.0.0.0:*    users:(("rpc.statd",pid=30812,fd=8)) uid:29 ino:56538 sk:1 cgroup:/system.slice/rpc-statd.service <->                      
udp   UNCONN 0      0            0.0.0.0:20048      0.0.0.0:*    users:(("rpc.mountd",pid=30816,fd=4)) ino:57317 sk:2 cgroup:/system.slice/nfs-mountd.service <->                           
udp   UNCONN 0      0            0.0.0.0:48846      0.0.0.0:*    ino:58679 sk:3 cgroup:unreachable:14e4 <->                                                                                 
udp   UNCONN 0      0            0.0.0.0:111        0.0.0.0:*    users:(("rpcbind",pid=30811,fd=5),("systemd",pid=1,fd=59)) ino:23586 sk:4 cgroup:/system.slice/rpcbind.socket <->          
udp   UNCONN 0      0          127.0.0.1:323        0.0.0.0:*    users:(("chronyd",pid=719,fd=5)) ino:19467 sk:5 cgroup:/system.slice/chronyd.service <->                                   
udp   UNCONN 0      0          127.0.0.1:884        0.0.0.0:*    users:(("rpc.statd",pid=30812,fd=5)) ino:56524 sk:6 cgroup:/system.slice/rpc-statd.service <->                             
udp   UNCONN 0      0               [::]:20048         [::]:*    users:(("rpc.mountd",pid=30816,fd=6)) ino:57325 sk:7 cgroup:/system.slice/nfs-mountd.service v6only:1 <->                  
udp   UNCONN 0      0               [::]:48968         [::]:*    users:(("rpc.statd",pid=30812,fd=10)) uid:29 ino:56546 sk:8 cgroup:/system.slice/rpc-statd.service v6only:1 <->            
udp   UNCONN 0      0               [::]:40906         [::]:*    ino:58681 sk:9 cgroup:unreachable:14e4 v6only:1 <->                                                                        
udp   UNCONN 0      0               [::]:111           [::]:*    users:(("rpcbind",pid=30811,fd=7),("systemd",pid=1,fd=61)) ino:23604 sk:a cgroup:/system.slice/rpcbind.socket v6only:1 <-> 
udp   UNCONN 0      0              [::1]:323           [::]:*    users:(("chronyd",pid=719,fd=6)) ino:19468 sk:b cgroup:/system.slice/chronyd.service v6only:1 <->                          
tcp   LISTEN 0      4096         0.0.0.0:20048      0.0.0.0:*    users:(("rpc.mountd",pid=30816,fd=5)) ino:57321 sk:c cgroup:/system.slice/nfs-mountd.service <->                           
tcp   LISTEN 0      4096         0.0.0.0:56857      0.0.0.0:*    users:(("rpc.statd",pid=30812,fd=9)) uid:29 ino:56542 sk:d cgroup:/system.slice/rpc-statd.service <->                      
tcp   LISTEN 0      64           0.0.0.0:39835      0.0.0.0:*    ino:58680 sk:e cgroup:unreachable:14e4 <->                                                                                 
tcp   LISTEN 0      50           0.0.0.0:445        0.0.0.0:*    users:(("smbd",pid=30660,fd=31)) ino:55890 sk:f cgroup:/system.slice/smb.service <->                                       
tcp   LISTEN 0      4096         0.0.0.0:111        0.0.0.0:*    users:(("rpcbind",pid=30811,fd=4),("systemd",pid=1,fd=55)) ino:23577 sk:10 cgroup:/system.slice/rpcbind.socket <->         
tcp   LISTEN 0      64           0.0.0.0:2049       0.0.0.0:*    ino:57398 sk:11 cgroup:unreachable:14e4 <->                                                                                
tcp   LISTEN 0      128          0.0.0.0:22         0.0.0.0:*    users:(("sshd",pid=42968,fd=3)) ino:98681 sk:12 cgroup:/system.slice/sshd.service <->                                      
tcp   LISTEN 0      50           0.0.0.0:139        0.0.0.0:*    users:(("smbd",pid=30660,fd=32)) ino:55891 sk:13 cgroup:/system.slice/smb.service <->                                      
tcp   LISTEN 0      4096            [::]:20048         [::]:*    users:(("rpc.mountd",pid=30816,fd=7)) ino:57329 sk:14 cgroup:/system.slice/nfs-mountd.service v6only:1 <->                 
tcp   LISTEN 0      64              [::]:39509         [::]:*    ino:58682 sk:15 cgroup:unreachable:14e4 v6only:1 <->                                                                       
tcp   LISTEN 0      4096            [::]:41679         [::]:*    users:(("rpc.statd",pid=30812,fd=11)) uid:29 ino:56550 sk:16 cgroup:/system.slice/rpc-statd.service v6only:1 <->           
tcp   LISTEN 0      50              [::]:445           [::]:*    users:(("smbd",pid=30660,fd=29)) ino:55888 sk:17 cgroup:/system.slice/smb.service v6only:1 <->                             
tcp   LISTEN 0      4096            [::]:111           [::]:*    users:(("rpcbind",pid=30811,fd=6),("systemd",pid=1,fd=60)) ino:23595 sk:18 cgroup:/system.slice/rpcbind.socket v6only:1 <->
tcp   LISTEN 0      64              [::]:2049          [::]:*    ino:57412 sk:19 cgroup:unreachable:14e4 v6only:1 <->                                                                       
tcp   LISTEN 0      128             [::]:22            [::]:*    users:(("sshd",pid=42968,fd=4)) ino:98690 sk:1a cgroup:/system.slice/sshd.service v6only:1 <->                             
tcp   LISTEN 0      50              [::]:139           [::]:*    users:(("smbd",pid=30660,fd=30)) ino:55889 sk:1b cgroup:/system.slice/smb.service v6only:1 <->                             
```

## firewall status
```text
public (active)
  target: default
  icmp-block-inversion: no
  interfaces: enp0s3 enp0s8
  sources: 
  services: cockpit dhcpv6-client http ssh
  ports: 445/tcp 2049/tcp
  protocols: 
  forward: yes
  masquerade: no
  forward-ports: 
  source-ports: 
  icmp-blocks: 
  rich rules: 
