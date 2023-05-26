The **init** goal is to make sure the system runs the right complement of services and daemons at any given time.

**init** maintains a notion of the mode in which the system should be operation, some commonly ones:
- *Single-user mode*: Only a minimal set of filesystems is mounted, no services are running, and a root shell is started on the console.
- *Multiuser mode*: All customary filesystems are mounted, and all configured network services has been started, along with a window system and graphical display manager for the console.
- *Server mode*: Usermode, but with no GUI.

Every mode is associated with a defined complement of system services, and the initialization daemon starts or stops services as needed.

**Init** normally takes care of:
- Setting the name of computer (host)
- Setting the timezone
- Checking disks with fsck
- Mounting filesystems
- Remove /tmp dir
- Configuring network interfaces
- Configuring packet filters
- Start other daemons and network services

**init** has very little built-in knowledge about these tasks, it just simply runs a set of command s or scripts that have been designated for execution in that particular context.

## Implementations of init:

