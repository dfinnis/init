# System commands on a Debian machine

See the [root Readme](https://github.com/dfinnis/init/blob/master/README.md) for how to setup the virtual machine.
<br>
<br>


**[1.](https://github.com/dfinnis/init/blob/master/system/01) In what file can you find the installed version of your Debian?**

/etc/debian_version
<br>
<br>


**[2.](https://github.com/dfinnis/init/blob/master/system/02) What command can you use to rename your system?**

```
sudo hostname this-is-the-new-hostname
```
To check the hostname, run: ```hostname```
<br>


**[3.](https://github.com/dfinnis/init/blob/master/system/03) What file has to be modified to make it permanent?**

/etc/hostname
<br>
<br>


**[4.](https://github.com/dfinnis/init/blob/master/system/04) What command gives you the time since your system was last booted?**

```
uptime
```
<br>


**[5.](https://github.com/dfinnis/init/blob/master/system/05) Name the command that determines the state of the SSH service**

```
/etc/init.d/ssh status
```
Or
```
sudo service ssh status
```
<br>


**[6.](https://github.com/dfinnis/init/blob/master/system/06) Name the command that reboots the SSH service**

```
sudo /etc/init.d/ssh restart
```
Or
```
sudo service ssh restart
```
<br>


**[7.](https://github.com/dfinnis/init/blob/master/system/07) Figure out the PID of the SSHD service**

```
/etc/init.d/ssh status | grep "Main PID"
```
PID is process ID
SSH is a Secure Shell Daemon application
<br>


**[8.](https://github.com/dfinnis/init/blob/master/system/08) What file contains the RSA keys of systems that are authorized to connect via SSH?**

~/.ssh/authorized_keys

RSA is a private key used for authentication +  secure data transmission
The encription key is public and the decription key is kept secret (private)
<br>
<br>


**[9.](https://github.com/dfinnis/init/blob/master/system/09) What command lets you know who is connected to the System?**

```
w
```
<br>


**[10.](https://github.com/dfinnis/init/blob/master/system/10) Name the command that lists the partition tables of drives?**

```
sudo fdisk -l
```
A partition table is a table maintained on disk by the operating system describing the partitions on that disk.
<br>


**[11.](https://github.com/dfinnis/init/blob/master/system/11) Name the command that displays the available space left and used on the system in an humanly understandable way**

```
df -h
```
<br>


**[12.](https://github.com/dfinnis/init/blob/master/system/12) Figure out the exact size of each folder of /var in a humanly understandable way followed by the path of it**

```
sudo du -sh /var/*
```
* du (disc usage) 
* -s = summarize
* -h = human-readable
<br>


**[13.](https://github.com/dfinnis/init/blob/master/system/13) Name the command that find, in real time, currently running processes**

```
top
```
<br>


**[14.](https://github.com/dfinnis/init/blob/master/system/14) Run the ‘tail -f /var/log/syslog‘ command in background**

```
sudo tail -f /var/log/syslog &
```
<br>


**[15.](https://github.com/dfinnis/init/blob/master/system/15) Find the command that kills the background command’s process**

```
sudo pkill tail
```
or
```
sudo pkill $1
```
or

to get PID of the process:
```
ps aux | grep tail
```
then
```
sudo kill -9 <PID>
```
<br>


**[16.](https://github.com/dfinnis/init/blob/master/system/16) Find the service which makes it possible to run specific tasks following a regular schedule**

```
cron
```
cron is the program and crontab is the command

crontab -e
As you can see, there are 5 stars. The stars represent different date parts
in the following order:

* minute (from 0 to 59)
* hour (from 0 to 23)
* day of the month (from 1 to 31)
* month (from 1 to 12)
* day of the week (from 0 to 6 | 0 = Sunday)

* * * * * /bin/execute/this/script.sh
<br>
<br>


**[17.](https://github.com/dfinnis/init/blob/master/system/17) Find the command that allows you to connect via ssh on the VM.(In parallel with the graphic session)**

```

```
<br>


**[18.](https://github.com/dfinnis/init/blob/master/system/18) Find the command that kills ssh service**

```

```
<br>


**[19.](https://github.com/dfinnis/init/blob/master/system/19) List all services which are started at boot time and name this kind of services**

```

```
<br>


**[20.](https://github.com/dfinnis/init/blob/master/system/20) List all existing users on the VM**

```

```
<br>


**[21.](https://github.com/dfinnis/init/blob/master/system/21) List all real users on the VM**

```

```
<br>


**[22.](https://github.com/dfinnis/init/blob/master/system/22) Find the command that add a new local user**

```

```
<br>


**[23.](https://github.com/dfinnis/init/blob/master/system/23) Explain how connect yourself as new user. (With graphic session and ssh session)**


<br>
<br>


**[24.](https://github.com/dfinnis/init/blob/master/system/24) Find the command that list all packages**

```

```
<br>

