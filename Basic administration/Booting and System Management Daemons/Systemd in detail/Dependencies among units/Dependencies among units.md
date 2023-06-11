> [!note]
> Linux software packages generally come with their own unit files, so you don't need a detailed knowledge of the entire configuration language.

To begin with, not all dependencies are explicit. For instance, **systemd** takes over the functions of the old **inetd** and also extends this idea into the domain of the D-Bus interprocess communication system.

Second, **systemd** makes some assumptions about the normal behavior of most kinds of units. For example, **systemd** assumes that the average service is an add-on that shouldn't be running during the early phase of system initialization and can be turned off by setting:
```ini
DefaultDependencies=false
```

A third class of dependencies are those explicitly declared in the [Unit] sections of unit files.

| Options   | Meaning                                                                  |
| --------- | ------------------------------------------------------------------------ |
| Wants     | Units that should be coactivated if possible, but are not required       |
| Requires  | Strict dependencies; failure of any prerequisite terminates this service |
| Requisite | Like *Requires*, but must already be active                              |
| BindsTo   | Similar to *Requires* but even more tightly coupled                      |
| PartOf    | Similar to *Requires*, but affects only starting and stopping            |
| Conflicts | Negative dependencies; cannot be coactive with these units                                                                         |

> The least restrictive variant, *Wants*, is preferred when possible

The command
```bash
sudo systemctl add-wants multi-user.target my.local.service
```
adds a dependency 