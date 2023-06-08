**systemctl** is an all-purpose command for investigating the status of **systemd** and making changes to its configuration.

Running **systemctl** without any arguments invokes the default **list-units** subcommand, which show all loaded and active services, sockets, targets, mounts, and devices. 
> To show only loaded and active devices, use **--type=service**

>[!info]
>It's also sometimes helpful to see all the installed unit files, regardless of their activeness by using **systemctl list-unit-files --type=service**

>[!note]
>For subcommands that act on a particular unit (e.g, **systemctl status**), **systemctl** can accept a unit name without a unit-type suffix (e.g., **cups** instead of **cups.service**)

---
###### Common used systemctl subcommands:

| Subcommand          | Function                                             |
| ------------------- | ---------------------------------------------------- |
| **list-unit-files** | Shows installed units; optionally matching pattern   |
| **enable**          | Enables unit to activate at boot                     |
| **disable**         | Prevents unit from activating at boot                |
| **isolate**         | Changes operating mode to target                     |
| **start**           | Actives unit immediately                             |
| **stop**            | Deactivates unit immediately                         |
| **restart**         | Restart (or starts, if not running) unit immediately |
| **status**          | Shows unit's status and recent log entries           |
| **kill**            | Sends a signal to units matching pattern             |
| **reboot**          | Reboot the computer                                  |
| **daemon-reaload**  | Reload unit files and **systemd** config             |
|                     |                                                      |



