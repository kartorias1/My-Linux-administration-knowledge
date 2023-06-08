```shell
$ sudo systemctl status -l cups
cups.service - CUPS Scheduler
Loaded: loaded (/lib/systemd/system/cups.service; disabled; vendor
preset: enabled)
Active: inactive (dead) since Sat 2016-12-12 00:51:40 MST; 4s ago
Docs: man:cupsd(8)
Main PID: 10081 (code=exited, status=0/SUCCESS)
Dec 12 00:44:39 ulsah systemd[1]: Started CUPS Scheduler.
Dec 12 00:44:45 ulsah systemd[1]: Started CUPS Scheduler.
Dec 12 00:51:40 ulsah systemd[1]: Stopping CUPS Scheduler...
Dec 12 00:51:40 ulsah systemd[1]: Stopped CUPS Scheduler.
```

>[!note]
>By default, the log entries are compressed to takes only one line, so we included the **-l** option to request full entries (useful habit to acquire).

###### Unit file statuses

| State        | Meaning                                                          |
| ------------ | ---------------------------------------------------------------- |
| **bad**      | Some kind of problem within **systemd**; usually a bad unit file |
| **disabled** | Present, but not configured to start autonomously                |
| **enabled**  | Installed and runnable; will start autonomously                  |
| **indirect** | Disabled, but has peers in Also clauses that may be enabled      |
| **linked**   | Unit file available through a symlink                            |
| **masked**   | Banished from the **systemd** world from a logical perspective   |
| **static**   | Depended upon by another unit; has no install requirement        |

