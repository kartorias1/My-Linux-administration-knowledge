Once the kernel has been loaded and completed its initialization process, it creates a complement of *spontaneous* process (start autonomously by the kernel).

Most of the spontaneous processes are part of kernel implementation, not necessarily correspond to a program in the filesystem, not configurable and don't require administrative attention.

>[!note]
>The system management daemon has process ID 1 and usually run under the name **init**. This daemon has a couple of special privileges, but fot the most part it's just a user-level program.

1. [[Responsibilities of init]]
2. [[Implementation of init]]
3. [[Traditional init]]
4. [[Systemd]]