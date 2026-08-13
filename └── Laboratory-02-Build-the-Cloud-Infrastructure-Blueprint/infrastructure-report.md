# Infrastructure Report (Variant 2: Table-First Format)

**Environment:** KillerCoda Playground

Fill in the table first, then paste supporting command output below each row if your instructor wants the raw terminal text too.

| # | Attribute | Command | Your Finding |
|---|---|---|---|
| 1 | Operating System | `cat /etc/os-release` (or `cat /etc/lsb-release`, `lsb_release -a`) | |
| 2 | Kernel Version | `uname -r` | |
| 3 | CPU Model | `lscpu` → Model name | |
| 4 | CPU Cores | `nproc` | |
| 5 | Total RAM | `free -h` → Mem total | |
| 6 | Disk Capacity | `df -h` | |
| 7 | Mounted File Systems | `df -hT` or `mount` | |
| 8 | Hostname | `hostname` | |
| 9 | IP Address | `ip addr show` or `hostname -I` | |

## Raw Command Output (optional, paste below if required)

```
$ cat /etc/os-release
<!-- paste -->

$ uname -r
<!-- paste -->

$ lscpu
<!-- paste -->

$ free -h
<!-- paste -->

$ df -h
<!-- paste -->

$ hostname
<!-- paste -->

$ ip addr show
<!-- paste -->
```
