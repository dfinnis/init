# Network Configuration Commands

**[1.](https://github.com/dfinnis/init/blob/master/network/01) Get the list of the network interfaces of the machine without displaying any detail for these interfaces. Only the list of names.**

```
ifconfig -l
```
<br>


**[2.](https://github.com/dfinnis/init/blob/master/network/02) Identify and display the Ethernet interface characteristics:**
  * Broadcast address <br>
  * All IP adresses which are part of the same subnet

```
ifconfig | grep broadcast | cut -f 6 -d ' '
ping 10.12.255.255
arp -a
```
<br>


**[3.](https://github.com/dfinnis/init/blob/master/network/03) Identify the MAC address of the Wi-Fi card**

```
ifconfig en1 | awk '/ether/{print $2}'
```
<br>


**[4.](https://github.com/dfinnis/init/blob/master/network/04) Identifiy the default gateway in the routing table**

```
route -n get default | grep gateway | cut -d ' ' -f 6
```
<br>


**[5.](https://github.com/dfinnis/init/blob/master/network/05) Identify the IP address of the DNS that responds to the following url: slash16.org**

```
nslookup slash16.org | grep Server | cut -d ':' -f 2 | tr -d '\t'
```
<br>


**[6.](https://github.com/dfinnis/init/blob/master/network/06) Get the complete path of the file that contains the IP address of the DNS server you’re using**

/etc/resolv.conf <br>
or <br>
/private/var/run/resolv.conf
<br>
<br>


**[7.](https://github.com/dfinnis/init/blob/master/network/07) Query an external DNS server on the slash16.org domain name (ie. : google 8.8.8.8)**

```
nslookup slash16.org 8.8.8.8
```
<br>


**[8.](https://github.com/dfinnis/init/blob/master/network/08) Find the provider of slash16.org**

```
ARG=`host slash16.org | grep 'address' | cut -d ' ' -f 4 | head -n 1`;
whois $ARG
```
Amazom AWS
<br>
<br>


**[9.](https://github.com/dfinnis/init/blob/master/network/09) Find the external IP of 42.fr**

163.172.250.13 <br>
163.172.250.12 <br>
163.172.250.11
<br>
<br>


**[10.](https://github.com/dfinnis/init/blob/master/network/10) Identify the network devices between your computer and the slash16.org domain**

```
traceroute slash16.org
```
<br>


**[11.](https://github.com/dfinnis/init/blob/master/network/11) Use the output of the previous command to find the name and IP address of the device that makes the link between you (local network) and the outside world**

```
traceroute slash16.org | grep 'nat'
```

It's the NAT server, the one with the nat name. <br>
Network address translation (NAT) is a method of remapping one IP address space into another by modifying network address information in the IP header of packets while they are in transit across a traffic routing device.
<br>
<br>


**[12.](https://github.com/dfinnis/init/blob/master/network/12) Find the IP that was assigned to you by dhcp server**

```
ifconfig | grep netmask | tail -n 1 | cut -d ' ' -f 2
```
<br>


**[13.](https://github.com/dfinnis/init/blob/master/network/13) Thanks to the previous question and the reverse DNS find the name of your host**

e2r3p3.42.fr
<br>
<br>


**[14.](https://github.com/dfinnis/init/blob/master/network/14) What file contains the local DNS entries?**

/etc/hosts
<br>
<br>


**[15.](https://github.com/dfinnis/init/blob/master/network/15) Make the intra.42.fr address reroute to 46.19.122.85**

in the /etc/hosts add a line:
46.19.122.85	intra.42.fr
<br>
<br>
