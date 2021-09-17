## Samples for Processes in Z and D State

The programs above are used for emulating processes in zombie and uninterruptible sleep state.  Below are steps for running the compiled programs.

### Zombie

```bash
./newzombie &
```

You can use top or ps to view the state.  Samples below.

#### Top

Once you run the program, filter by processes in a "Z" state by typing "o" then S=Z.

```bash
root@aa4e7798b9f1:/home/tests# ./newzombie &
[1] 1751
root@aa4e7798b9f1:/home/tests# top

top - 20:52:22 up 45 days, 10:30,  5 users,  load average: 0.66, 0.81, 0.88
Tasks:  25 total,   1 running,  22 sleeping,   0 stopped,   1 zombie
%Cpu(s):  2.4 us,  2.4 sy,  0.7 ni, 94.3 id,  0.3 wa,  0.0 hi,  0.0 si,  0.0 st
KiB Mem :  1975528 total,   141132 free,   929160 used,   905236 buff/cache
KiB Swap:  1910780 total,  1141648 free,   769132 used.   772276 avail Mem

  PID USER      PR  NI    VIRT    RES    SHR S %CPU %MEM     TIME+ COMMAND
 1752 root      30  10       0      0      0 Z  0.0  0.0   0:00.00 newzombie
```

### D State

Similar to the zombie process but filter in top using "S=D".
```bash
root@aa4e7798b9f1:/home/tests# ./dproc &
[1] 1770
root@aa4e7798b9f1:/home/tests# top

top - 21:04:22 up 45 days, 10:42,  5 users,  load average: 2.00, 0.99, 0.85
Tasks:  23 total,   1 running,  22 sleeping,   0 stopped,   0 zombie
%Cpu(s):  2.0 us,  1.0 sy,  0.7 ni, 96.3 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
KiB Mem :  1975528 total,   110100 free,   932656 used,   932772 buff/cache
KiB Swap:  1910780 total,  1139524 free,   771256 used.   773128 avail Mem

  PID USER      PR  NI    VIRT    RES    SHR S %CPU %MEM     TIME+ COMMAND
 1770 root      30  10    4032    588    524 D  0.0  0.0   0:00.00 dproc
```

### Usage

You can use the following command to download and unzip the contents or you can just a git clone.

```bash

wget -c https://github.com/azureossd/linux-monitoring-tools-samples/archive/refs/heads/master.zip && unzip master.zip

```

The contents will be extracted as shown below.

```bash

root@6cc2a4520825:/home#wget -c https://github.com/azureossd/linux-monitoring-tools-samples/archive/refs/heads/master.zip && unzip master.zip
--2021-09-17 21:45:53--  https://github.com/azureossd/linux-monitoring-tools-samples/archive/refs/heads/master.zip
Resolving github.com (github.com)... 192.30.255.112
Connecting to github.com (github.com)|192.30.255.112|:443... connected.
HTTP request sent, awaiting response... 302 Found
Location: https://codeload.github.com/azureossd/linux-monitoring-tools-samples/zip/refs/heads/master [following]
--2021-09-17 21:45:54--  https://codeload.github.com/azureossd/linux-monitoring-tools-samples/zip/refs/heads/master
Resolving codeload.github.com (codeload.github.com)... 192.30.255.121
Connecting to codeload.github.com (codeload.github.com)|192.30.255.121|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 7085 (6.9K) [application/zip]
Saving to: 'master.zip'

master.zip          100%[===================>]   6.92K  --.-KB/s    in 0s

2021-09-17 21:45:54 (75.5 MB/s) - 'master.zip' saved [7085/7085]

Archive:  master.zip
70959167a7d8681516ca2c671756ea32d90eb74a
   creating: linux-monitoring-tools-samples-master/
  inflating: linux-monitoring-tools-samples-master/README.md
  inflating: linux-monitoring-tools-samples-master/dproc
  inflating: linux-monitoring-tools-samples-master/dproc.c
  inflating: linux-monitoring-tools-samples-master/newzombie
  inflating: linux-monitoring-tools-samples-master/zombie.c
root@6cc2a4520825:/home# ls -ltra
total 12
drwxrwxrwx  2 nobody nogroup    0 Apr 30 00:06 ASP.NET
drwxrwxrwx  2 nobody nogroup    0 Apr 30 00:06 site
drwxrwxrwx  2 nobody nogroup    0 Sep 17 21:09 linux-monitoring-tools-samples-master
drwxrwxrwx  2 nobody nogroup    0 Sep 17 21:18 LogFiles
drwxr-xr-x 94 root   root    4096 Sep 17 21:18 ..
-rwxrwxrwx  1 nobody nogroup 7085 Sep 17 21:45 master.zip
drwxrwxrwx  2 nobody nogroup    0 Sep 17 21:45 .
root@6cc2a4520825:/home#
