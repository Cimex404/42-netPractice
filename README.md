#  netPrectice 42

This is a 42 project that teaches about IP addresses and networks.

##  What is an IP addresses?

<p>
An IP address may look something like this:
<blockquote>
  172.201.30.147
</blockquote>

Essentialy is is a 4-byte, 32-bit binary. Another way to write this IP address would be:
<blockquote>
  10101100.11001001.00011110.10010011
</blockquote>

An IP address is used to identify a specific device within a network. A network as a system comprised of at least two devices that can share data.
</p>

An IP is made of two parts:
-  Network portion
-  Host portion
<p>
The <strong>Network portion (172.201.30.---)</strong> is used to identify the network itself. This is because networks can also communicate with other networks using devices such as routers.
</p>
<p>
The <strong>Host portion (---.---.---.147)</strong> is used to identify a specific device within a network.
</p>

##  Masks
If the network and host portions are set to be 3 and 1 byte respectively, does that mean that there are only a maximum of 256 devices allowed to be in a network at the same time? No.
Because the size of the network and host portion is variable, because of something called a **Mask**.

A mask notes the size of the network portion of an IP address and is usually written in the same format.
<blockquote>
255.255.255.0
</blockquote>

This mask signifies, that the host portion of the network has a size of 256 IP addresses.

<blockquote>
255.255.255.128
</blockquote>

This is a size of 129.

<blockquote>
255.255.255.240
</blockquote>

This is a size of 17.

##  CIDR notation
The Mask can also be be written in a different way. The **CIDR** notation is a more compact version of the notation we just looked at. Here is a conversion table:

```
Mask                CIDR        Number of IP's
-------------------------------------------------
255.255.255.255     /32         1
255.255.255.254     /31         2
255.255.255.252     /30         4
255.255.255.248     /29         8
255.255.255.240     /28         16
255.255.255.224     /27         32
255.255.255.192     /26         64
255.255.255.128     /25         128
255.255.255.0       /24         256
255.255.254.0       /23         512
255.255.252.0       /22         1024
255.255.248.0       /21         2048
255.255.240.0       /20         4096
255.255.224.0       /19         8192
255.255.192.0       /18         16384
255.255.128.0       /17         32768
255.255.0.0         /16         65536
255.254.0.0         /15         131072
255.252.0.0         /14         262144
255.248.0.0         /13         524288
255.240.0.0         /12         1048576
255.224.0.0         /11         2097152
255.192.0.0         /10         4194304
255.128.0.0         /9          8388608
255.0.0.0           /8          16777216
254.0.0.0           /7          33554432
252.0.0.0           /6          67108864
248.0.0.0           /5          134217728
240.0.0.0           /4          268435456
224.0.0.0           /3          536870912
192.0.0.0           /2          1073741824
128.0.0.0           /1          2147483648
0.0.0.0             /0          4294967296
```

IP addresses also contain the Network address, which is the very first address in a network. It represents the entire network and serves as the starting point, no device of the network can have the same IP as the network IP.
The same goes for the last IP of the network, which is called the broadcast IP.

That means that networks with the masks /32 and /31 can not contain any devices as they don't have any usable IP's for devices.


##  How netPracice works
<p>
  NetPractice is a simulation of real networks. You are given a problem with one or multiple faulty networks and by changing the IP addresses, masks and routes of some devices, you need to make the networks function based on some criteria.
  Here is an example of a simple problem:
</p>
<p>
  <img src="https://github.com/Cimex404/42-netPractice/blob/master/Example.png" alt="Example Network" width="500">
</p>


##  Solutions
<details>
  <summary>Level 1</summary>
  <p>
    <strong>Level 1</strong> is simply figuring out that IP addresses can't be the same, but must be within the same mask. To achieve this, you must fix two networks, that have the same problem. Childsplay.
  </p>
  <p>
    <img src="https://github.com/Cimex404/42-netPractice/blob/master/Solutions/Level1.png" alt="Level 1" width="1200">
  </p>
</details>

<details>
  <summary>Level 2</summary>
  <p>
    <strong>Level 2</strong> is in concept, the same as level 1, but there is a Mask mismatch for the first network. So you need to learn, that masks MUST be same same among a single network. Easy as pie.
  </p>
  <p>
    <img src="https://github.com/Cimex404/42-netPractice/blob/master/Solutions/Level2.png" alt="Level 2" width="1200">
  </p>
</details>

<details>
  <summary>Level 3</summary>
  <p>
    <strong>Level 3</strong> is about switches. Switches are cross-sections between devices, they do NOT link to other networks, but are contained inside them. Can do this with my eyes closed.
  </p>
  <p>
    <img src="https://github.com/Cimex404/42-netPractice/blob/master/Solutions/Level3.png" alt="Level 3" width="1200">
  </p>
</details>

<details>
  <summary>Level 4</summary>
  <p>
    <strong>Level 4</strong> is an introduction to routers. Other than switches, routers can connect to multiple networks and communicate between them. This is however not needed to solve this level, because in practice, this is the exact same as level 3. Ctrl+C Ctrl+V from Level 3
  </p>
  <p>
    <img src="https://github.com/Cimex404/42-netPractice/blob/master/Solutions/Level4.png" alt="Level 4" width="1200">
  </p>
</details>

<details>
  <summary>Level 5</summary>
  <p>
    <strong>Level 5</strong> is the first level with multiple networks that communicate with each other. Using a rounter, the hosts A and B need to find a connection. The second thing that is introduced, are routing tables, these show, where a particular device wants to send data and what the next stop is on it's path. New concept, but still somewhat easy.
  </p>
  <p>
    <img src="https://github.com/Cimex404/42-netPractice/blob/master/Solutions/Level5.png" alt="Level 5" width="1200">
  </p>
</details>

<details>
  <summary>Level 6</summary>
  <p>
    <strong>Level 6</strong> introduces the InTeRnEt!!! This one is pretty staight forward, connect the laptop to the rounter and connect the rounter to the iNtErNeT!!! Ok, ramping up the difficulty.
  </p>
  <p>
    <img src="https://github.com/Cimex404/42-netPractice/blob/master/Solutions/Level6.png" alt="Level 6" width="1200">
  </p>
</details>

<details>
  <summary>Level 7</summary>
  <p>
    <strong>Level 7</strong> is the C of this project. You need to connect two routers, that are each connected to a host. I recommend you use the same IP for all three networks. Of course, make sure that the masks are small enough to leave space for all connections, a /24 is too big. Now this is getting tricky.
  </p>
  <p>
    <img src="https://github.com/Cimex404/42-netPractice/blob/master/Solutions/Level7.png" alt="Level 7" width="1200">
  </p>
</details>

<details>
  <summary>Level 8</summary>
  <p>
    In <strong>Level 8</strong> you are forced to do something called subnetting. basically, you HAVE to use the IP that is provided in the left part of the Internets routing table for all other networks. Take a good look at the CIDR notation right after it, this is the amount of addresses that are available. I just saved you hours of headaches.
  </p>
  <p>
    <img src="https://github.com/Cimex404/42-netPractice/blob/master/Solutions/Level8.png" alt="Level 8" width="1200">
  </p>
</details>

<details>
  <summary>Level 9</summary>
  <p>
    <strong>Level 9</strong> is part one of IP-hell itself. You are given minimal rescrictions to work with, but this wont make it easier. You must make sure to pick the correct mask size for each network, I found it easiest to use /28 as this gives you some room, but also is small enough not to trip any other networks. Now this is difficult.
  </p>
  <p>
    <img src="https://github.com/Cimex404/42-netPractice/blob/master/Solutions/Level9.png" alt="Level 9" width="1200">
  </p>
</details>

<details>
  <summary>Level 10</summary>
  <p>
    <strong>Level 10</strong> is part two of IP-hell. When it comes down to it, Level 10 and Level 9 are pretty much the same, except that Level 10 restricts you more, but this actually makes it easier then Level 9. Easier, but still hard.
  </p>
  <p>
    <img src="https://github.com/Cimex404/42-netPractice/blob/master/Solutions/Level10.png" alt="Level 10" width="1200">
  </p>
</details>


#	A little word of encouragement
<p>
	If you want to make sure you understand everything, keep playing through the levels, over and over.
	It may start to get tiring, but trust me, after a while you have made every mistake possible and you'll know what do to to fix it.
	Also, google for a CIDR-conversion table and keep it docked while training, this will massively help you.
</p>
<p>
	This is it from me.
	Thank you and good luck with your netPractice. :)
</p>
