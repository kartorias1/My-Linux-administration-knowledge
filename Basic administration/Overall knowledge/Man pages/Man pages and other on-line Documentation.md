## Organization of the man pages
![[Pasted image 20220912105312.png|center]]

The exact structure of the sections isn’t important for most topics because man finds the appropriate page wherever it is stored.

> Be aware of the section definitions when a topic with the same name appears in multiple sections. For example, passwd is both a command and a configuration file, so it has entries in both section 1 and section 5.

### man:read man pages
**man** *title* formats a specific manual page and sends it to your terminal through  
**more**, **less**, or whatever program is specified in your PAGER environment variable.

The form **man** *section title* gets you a man page from a particular section. Thus, on most systems, **man sync** gets you the man page for the **sync** command, and **man 2 sync** gets you the man page for the **sync** system call.

### Storage of man pages

**nroff** input for man pages (i.e., the man page source code) is stored in directories under **/usr/share/man** and compressed with **gzip** to save space. The man command knows how to decompress them on the fly.

The **man** command can search several man page repositories to find the manual pages you request. On Linux systems, you can find out the current default search path with the **manpath** command. This path (from Ubuntu) is typical:

```bash
$ manpath 
  /usr/local/man:/usr/local/share/man:/usr/share/man
```

>[!note]
>If necessary, you can set your MANPATH environment variable to override the default path: 
>```bash
>$ export MANPATH=/home/share/localman:/usr/share/man
>```