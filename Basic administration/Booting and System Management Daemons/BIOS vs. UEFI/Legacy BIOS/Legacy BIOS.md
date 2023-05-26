This firmware assumes that the boot device starts with a record called the MBR (Master Boot Record). MBR includes
- A First-stage bootloader (boot block).
- Primitive disk partitioning table.
> The amount of space available for the bootloader i so small (less than 512 bytes) that it's just can load and run a second stage bootloader.

**Volume boot record**: The boot block reads the partitioning information from the MBR and identifies the disk partition marked as "active". It then reads and executes the second-stage bootloader from the beginning of that partition.

>[!note]
>To effect a successful boot, all components of the boot chain must be properly in stalled and compatible with one another.The second-stage loader is generally knowledgeable about OS and filesystems, and usually has configuration options of its own.