>When a machine is powered on, the CPU is hardwired to execute boot code stored in ROM.

The system firmware typically knows about all the devices that live on the motherboard, such as SATA controllers, network interfaces, USB controllers, and sensors for power and temperature.

On physical (as opposed to virtualized) hardware, most firmware offers a user interface. You need the control of the computer and console, and must press a particular key immediately after powering on the system in order to get to access.

During normal bootstrapping, the system firmware 
- Probes for hardware and disks.
- Runs a simple set of health checks.
- Looks for the next stage of bootstrapping code. 

The firmware UI lets you designate a boot device, usually by prioritizing a list of available options.

>[!note]
>This basically is what we called a *Boot option* (or *Boot menu*).