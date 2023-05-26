Kernel startup options typically:
- Modify the values of kernel parameters. 
- Instruct the kernel to probe for particular devices.
- Specify the path to the **init** or **systemd** process.
- Or designate a particular root device.

>[!note]
>When specified at boot time, kernel options are not persistent. Edit the appropriate kernel line in */etc/grub.d/40_custom* or */etc/defaults/grub* (the variable named GRUB_CMDLINE_LINUX) to make the change permanent across reboots.

Security patches, bug fixes, and features are all regularly added to the Linux kernel.

Unlike other software packages, however, new kernel releases typically do not replace old ones. Instead, the new kernels are installed side by side with the previous versions so that you can return to an older kernel in the event of problems.