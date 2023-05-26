GRUB lets you specify parameters such as the kernel to boot ("menu entry") and the operating system mode to boot into.

The GRUB config file is called **grub.cfg**, and it’s usually kept in */boot/grub* (*/boot/grub2* in Red Hat and CentOS) along with a selection of other resources and code modules that GRUB might need to access at boot time.

Although you can create the **grub.cfg** file yourself, it’s more common to generate it with the **grub-mkconfig** utility, which is called **grub2-mkconfig** on Red Hat and CentOS and wrapped as **update-grub** on Debian and Ubuntu.

>[!important]
>Most distributions assume that **grub.cfg** can be regenerated at will, and they do so automatically after updates. If you don’t take steps to prevent this, your handcrafted **grub.cfg** file will get clobbered.

The most commonly method to configure **grub-mkconfig** is specified the configuration in */etc/default/grub* in the form of *shell* variable assignments.

### Common GRUB configuration options
![[Pasted image 20220927195634.png|center]]

After editing */etc/default/grub*, run **update-grub** or **grub(2)-mkconfig** to translate your configuration into a proper **grub.cfg** file. As part of the configuration-building process, these commands inventory the system’s bootable kernels, so they can be useful to run after you make kernel changes even if you haven’t explicitly changed the GRUB configuration.

You may need to edit the */etc/grub.d/40_custom* file to change the order in which kernels are listed in the boot menu (after you create a custom kernel, for example), set a boot password, or change the names of boot menu items.
>Remember to run grub update command after making changes.