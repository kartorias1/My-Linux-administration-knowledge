The bootloader's main job is to identify and load an appropriate operating system kernel. Most bootloaders can also present a boot-time UI that lets you select which of several possible kernels or operating systems to invoke.

Another task that falls to the boot loader is the marshaling of configuration arguments for the kernel. The kernel doesn’t have a command line per se, but its startup option handling will seem eerily similar from the shell.

>[!note]
>Such options can be hard-wired into the boot loader’s configuration if you want them used on every boot, or they can be provided on the fly through the boot loader’s UI.