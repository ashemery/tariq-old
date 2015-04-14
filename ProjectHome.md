# A Hybrid Port Knocking System, #

The network security has become a primary concern on the Internet in order to provide protected communication between hosts/nodes in a hostile environment. In order to protect network resources, each service provider pose a number of nontrivial challenges to security design and set its own policies for accessing resources on the network. These challenges make a case for building security solutions that achieve both broad protection and desirable network performance in terms of minimum data overhead and delay. It is so crucial to have computationally cheap and simple defense mechanisms that allow early protection against all types of attacks. In particular, it becomes very common and useful to have multiple progressively stronger layers of security, rather than attempting to have a single perfect security layer.


## Port-Knocking History: ##

In computer networking, Port Knocking is a method of externally opening ports on a firewall by generating a connection attempt on a set of pre-specified closed ports. Once a correct sequence of connection attempts is received, the firewall rules are dynamically modified to allow the host which sent the connection attempts to connect over specific port(s)  [[1](http://en.wikipedia.org/wiki/Port_knocking/)].

The problem today in the world full of security threats, it should be assumed that all traffic is monitored by an unknown third party as it travels across a network. Doggedly adhering to this viewpoint provides us with the fact that our knock sequence can be passively observed by an eavesdropping person in the middle of our connection and just replay the knock sequence to get the same response from the server (open port or perform a task). This problem is called “TCP Replay Attack”. So we had to find a solution were the knock sequence is not re-playable.


## Tariq Overview: ##

Tariq is a new hybrid port-knocking technique, that uses Cryptography, Steganography, and Mutual Authentication to develop another security layer in front of any service that needs to be accessed from different locations around the globe. Tariq can be used for host authentication to make local services invisible from port scanning, provide an extra layer of security that attackers must penetrate before accessing or breaking anything important, act as a stop-gap security measure for services with known unpatched vulnerabilities, and provide a wrapper for a legacy or proprietary services with insufficient integrated security.

Tariq is developed using python and scapy to fulfil my Ph.D. Research. I chose python, because its an easy to learn language and the code can be easily audited or studied by others. I had to use a new methodology that can communicate in an unseen manner, making TCP Replay Attacks hard to be issued against Tariq. I also wanted the implementation to listen to no ports, or bind itself to no socket for packets exchange, so that Tariq won't be exposed itself to a remote exploit. Tariq relies completely on Packet Crafting, as all packets sent and received are crafted to suite its needs. Tariq doesn't just open/close ports, it can be used to perform remote tasks without the need to login to the remote box where Tariq is installed. All data sent and recived by Tariq is hidden within a PNG image using steganogra-py  [[2](http://code.google.com/p/steganogra-py/)], and encrypted using GnuPG. The current version of Tariq uses only the TCP protocol, but I am willing to make another version of Tariq were the user has the ability to choose the communication protocol used.


### This project was done to fulfill the requirements of my Ph.D. Thesis ... ###

## Old Project, no longer updated, check new PROJECT HERE: ##
> `[1]` https://github.com/ashemery/tariq/ <br>