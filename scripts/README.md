# Scripts

These scripts are designed to run on a debian virtual machine, see the [root Readme](https://github.com/dfinnis/init/blob/master/README.md) for setup.
<br>
<br>

**[1.](https://github.com/dfinnis/init/blob/master/scripts/01) Display only the login, UID and Path of each entry of the /etc/passwd file**

```
cat /etc/passwd | cut -d : -f 1,3,6 | sed 's/:/ /g' | column -t
```
<br>

**[2.](https://github.com/dfinnis/init/blob/master/scripts/02) Delete an active user on the VM**

```
if [ $(id -u $1) -eq $(id: ‘$1’: no such user)];then
	echo "no user: $1"
else
	echo "locking $1 account"
	sudo passwd --lock $1
	echo "finding $1 precesses"
	sudo pgrep -u $1
	echo "killing $1 processes"
	sudo pkill -9 -u $1
	echo "deleting user"
	sudo deluser --remove-home $1
	echo "user $1 deleted"
fi
```
<br>

**[3.](https://github.com/dfinnis/init/blob/master/scripts/03) Display all real (human) users**

```
cut -d: -f1,3 /etc/passwd | egrep ':[0-9]{4}$' | cut -d: -f1
```
