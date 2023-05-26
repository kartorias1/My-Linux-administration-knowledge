In the traditional init world, **system modes** (single user or multiuser) are known as *run levels*.
> Think of run levels as operating state of the OS, such as **single user mode**, **Multiuser mode**, **reboot**, ...

The traditional **init** is not really powerful on its own. Most modern systems that use it actually have a standard and fixed **init** configuration. These configuration points to a second tier of shell scripts that do the actual work (changing run levels, change configurations).

This second layer maintains yet a third layer of daemon and system specific scripts, which are cross-linked to run-level-specific directories that indicate what services are supposed to be running at what run level.

>[!note]
>This system requires all startups and takedowns be run at numeric order, this lead to the impossible in parallel execution and long time changing states.