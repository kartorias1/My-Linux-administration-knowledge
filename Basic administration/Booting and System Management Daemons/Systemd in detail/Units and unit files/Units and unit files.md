>[!note]
>An entity that is managed by **systemd** is known generically as a **unit**.

More specifically, a unit can be a service, a socket, a device, a mount point, an automount point, a swap file (or partition), a startup target, a watched filesystem path, a timer controlled and supervised by **systemd**, a resource management slice, a group of external processes, ...

>[!note]
>The behavior of each unit is defined and configured by a unit file.

> For example: The unit file for a service specifies the location of the executable file for the daemon, tells **systemd** how to start and stop the service, and identifies any other units that the service depends on

An example unit file for **rsync** daemon:

``` ini
[Unit]
Description=fast remote file copy program daemon
ConditionPathExists=/etc/rsyncd.conf
[Service]
ExecStart=/usr/bin/rsync --daemon --no-detach
[Install]
WantedBy=multi-user.target
```
> This is the format used by MS-DOS **.ini** files

Unit files can live in several places:
- **/usr/lib/systemd/system** is the main place where packages deposit their unit files during installation.
- **/lib/systemd/system** is used on some systems instead.

Local unit files and customizations can go in **/etc/systemd/system**

By convention, unit files are named with a suffix that according to the type of unit being configured.
For example, service units have a **.service** suffix and timers use **.timer**.
Within the unit file, [unit] apply to all kinds of units, but [Service] can appear only in the context of a particular unit type.