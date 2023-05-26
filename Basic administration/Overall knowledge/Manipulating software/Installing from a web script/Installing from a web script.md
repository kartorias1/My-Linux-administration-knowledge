Cross-platform software bundles increasingly offer an expedited installation process that’s driven by a *shell script* you download from the web with **curl**, **fetch**, or **wget**.

For example, to set up a machine as a Salt client, you can run the following commands:

```bash
$ curl -o /tmp/saltboot -sL https://bootstrap.saltstack.com  
$ sudo sh /tmp/saltboot
```

The bootstrap script investigates the local environment, then downloads, install, and configures an appropriate version of the software.

