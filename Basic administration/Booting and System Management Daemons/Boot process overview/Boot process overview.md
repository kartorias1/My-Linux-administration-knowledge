Most Linux distributions now use a system manager daemon called **systemd** instead of the traditional UNIX **init**. **systemd** streamlines the boot process by adding dependency management, support for a concurrent startup process, and a comprehensive approach to logging, among other features.

>[!note]
>During bootstrapping, the kernel is loaded into memory and begins to execute. A variety of initialization tasks are performed, and the system is then made available to users.
>![[Pasted image 20220913203035.png|center]]

Administrators have little direct, interactive control over most of the steps required to boot a system. Instead, admins can modify bootstrap configurations by
- Edit the config files for the system startup scripts.
- Change the arguments the bootloader passed to the kernel.

>Before the system is fully booted, filesystems must be checked and mounted and system daemons started. These procedures are managed by a series of shell scripts (sometimes called “**init** scripts”) or unit files that are run in sequence by **init** or parsed by **systemd**.