# init

Intro to system & network administration.

1. [**network**](https://github.com/dfinnis/init/tree/master/network) -  Network configuration commands.

2. [**system**](https://github.com/dfinnis/init/tree/master/system) - System commands on a Debian machine.

3. [**scripts**](https://github.com/dfinnis/init/tree/master/scripts) - Scripts to see & delete users.

See the [subject](https://github.com/dfinnis/init/blob/master/subject.pdf) for more details.

*Final Score 99/100*


## Debian Virtual Machine

*system* and *scripts* must be done on a Debian virtual machine.

Download this [debian disk image](https://cdimage.debian.org/debian-cd/current/i386/iso-cd/debian-10.8.0-i386-netinst.iso), you'll find documentation [here](https://cdimage.debian.org/debian-cd/current/i386/iso-cd/).


### Create Virtual Machine

On Mac OSX, install [VirtualBox](https://www.virtualbox.org/).

In VirtualBox create a new VM (click new).

* Name and operating system - Type: Linux, Version: (Debian 64-bit)

Continue through all the next steps with the default settings:

* Memory size: 4MB
* Hard disk: Create a disk now
* Hard disk file type: VDI(VirtualBox Disk Image)
* Storage on physical hard disk: Dynamically allocated
* File size: 12,00GB

Next click Settings > Network > Adapter 1 > Attached to: Bridged Adapter.

Still in settings click Storage > Right of "Controller: IDE", there is a CD icon with a + sign (add optical drive).
Click Add Disk Image, and select *debian-10.8.0-i386-netinst.iso*.

Click Start to start the VM.


### Install Debian

Continue through the next steps with the default settings:

* Graphical Install
* Language: English
* Location: United States
* Configure Keyboard: American English

...wait a minute...

* Hostname: debian
* Domain name: (none)
* Root password: (choose a password)
* Full name: (choose a name)
* Username: (choose a username)
* User password: (choose a password)
* Time zone: Eastern

...wait a second...

* Partition disks: Guided - use entire disk
* Select disk: SCS12 (0,0,0) (sda) - 8.6 GB ATA VBOX HARDDISK
* Partitioning scheme: All files in one partition
* Finish partitioning
* Write changes: Yes

...wait a minute...

* Software to install, add: SSH server & KDE Plasma

...wait 2 minutes...

* Install GRUB boot loader: Yes
* Device: /dev/sda

...wait a second...

* Finish installation

...wait a minute...


### Log in

Log in with your password.

Click on the icon in the bottom left, search for *terminal*, open *terminal*.

Switch from *user* to *root*. <br>
```su root```

Now you are ready to execute commands shown in [*system*](https://github.com/dfinnis/init/tree/master/system) and [*scripts*](https://github.com/dfinnis/init/tree/master/scripts).
