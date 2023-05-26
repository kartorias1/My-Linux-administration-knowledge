The UEFI specification includes a modern disk partitioning scheme known as GPT (GUID Partition Table, where GUID stands for “globally unique identifier”).

>[!note]
>UEFI also understands FAT (File Allocation Table) filesystems, a simple but functional layout that originated in MS-DOS.

At boot time, the firmware consults the GPT partition table to identify the ESP. It then reads the configured target application directly from a file in the ESP and executes it. 

>[!info]
>In fact, no bootloader at all is technically required since the Kernel can be configured for direct UEFI loading. But in practice, most systems still use a bootloader, partly because that makes it easier to maintain compatibility with legacy BIOSes.

UEFI saves the path name to load from the ESP as a configuration parameter. In example on modern systems: `/efi/boot/bootx64.efi`

UEFI defines standard APIs for accessing the system’s hardware. In this respect, it’s something of a miniature operating system in its own right. It even provides for UEFI-level add-on device drivers, which are written in a processor-independent language and stored in the ESP.

Because UEFI has a formal API, you can examine and modify UEFI variables (including boot menu entries) on a running system.

```shell

$ efibootmgr -v
BootCurrent: 0004  
BootOrder: 0000,0001,0002,0004,0003  
Boot0000* EFI DVD/CDROM PciRoot(0x0)/Pci(0x1f,0x2)/Sata(1,0,0)  
Boot0001* EFI Hard Drive PciRoot(0x0)/Pci(0x1f,0x2)/Sata(0,0,0)  
Boot0002* EFI Network PciRoot(0x0)/Pci(0x5,0x0)/MAC(001c42fb5baf,0)  
Boot0003* EFI Internal Shell MemoryMapped(11,0x7ed5d000,0x7f0dcfff)/  
FvFile(c57ad6b7-0515-40a8-9d21-551652854e37)  
Boot0004* ubuntu HD(1,GPT,020c8d3e-fd8c-4880-9b61-  
ef4cffc3d76c,0x800,0x100000)/File(\EFI\ubuntu\shimx64.efi)

```

**efibootmgr** lets you change the boot order, select the next configured boot option, or even create and destroy boot entries

>[!caution]
>systems (typically, those with systemd) that allow write access by default, **rm -rf /** can be enough to permanently destroy the system at the firmware level; in addition to removing files, **rm** also removes variables and other UEFI information accessible through /sys.