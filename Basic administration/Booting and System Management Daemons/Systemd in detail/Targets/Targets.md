Unit files can declare their relationships to other units in a variety of ways.
For example:
```ini
[Install]
WantedBy=multi-user.target
```
The *WantedBy* clause says that if the system has a **multi-user.target** unit, that unit should depend on this one (**rsync.service**) when this unit is enabled.


