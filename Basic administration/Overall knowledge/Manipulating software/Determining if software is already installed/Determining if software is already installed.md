If **which** can’t find the command you’re looking for, try **whereis**; it searches a broader range of system directories and is independent of your shell’s search path.

Another alternative is the incredibly useful **locate** command, which consults a precompiled index of the filesystem to locate filenames that match a particular pattern.

>FreeBSD includes locate as part of the base system. On Linux, the current implementation of locate is in the mlocate package. On Red Hat and CentOS, install the mlocate package with yum.

>[!note]
>**locate**’s database is updated periodically by the **updatedb** command (in FreeBSD, **locate.updatedb**), which runs periodically out of **cron**. Therefore, the results of a **locate** don’t always reflect recent changes to the filesystem.