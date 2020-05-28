<p align="center">
<font size="5">
  <b>OSCP</b><br>
</font>
 <img src="oscp1.png">
</p>


# Find File:

**locate**
```
updatedb
```
to update the file index database

```
locate *filename*
```
**which**

find the file wich has current execution envirnoment

```
which *part of file name*
```

**find**

powerfull search tool with many arguments

```
find *search location*  -name *filename* -exec file "{}"\;
```

# Service managent:

```
service *service name* [option]

```
option could be : start, stop, or restart

alternatevly you can use:

```
/etc/init.d/*service name* [option]
```

or:

```
update-rc.d *servicename* [options]

```

options here are: defaults, remove, start , or stop



**GUI service management:**

rcconf

![Alt text](rcconf.png)


sysv--rc-conf

![Alt text](sysv-rc-conf.png)
