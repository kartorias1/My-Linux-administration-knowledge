Unit files can declare their relationships to other units in a variety of ways.
For example:
```ini
[Install]
WantedBy=multi-user.target
```
The *WantedBy* clause says that if the system has a **multi-user.target** unit, that unit should depend on this one (**rsync.service**) when this unit is enabled.

Because units directly support dependency management, no additional machinery is needed to implement the equivalent of **init**'s run levels.

>[!note]
>The only targets to really be aware of are **multi-user.target** and **graphical.target** for day-to-day use, and **rescue.target** for accessing single-user mode.
>To change this current operating mode, use **systemctl isolate** command:
>
>```shell
>$ sudo systemctl isolate multi-user.target
>```

###### Mapping between init run levels and systemd targets

| Run level    | Target                | Description                            |
| ------------ | --------------------- | -------------------------------------- |
| 0            | **poweroff.target**   | System halt                            |
| emergency    | **emergency.target**  | Bare-bones shell for system recovery   |
| 1, s, single | **rescure.target**    | Single-user mode                       |
| 2            | **multi-user.target** | Multiuser mode (command line)          |
| 3            | **multi-user.target** | Multiusermode with networking          |
| 4            | **multi-user.target** | Not normally used by **init**          |
| 5            | **graphical.target**  | Multiuser mode with networking and GUI |
| 6            | **reboot.target**     | System reboot                          |

