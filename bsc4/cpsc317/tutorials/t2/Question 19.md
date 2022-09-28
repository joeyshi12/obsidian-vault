**Question:**

In the same network diagram for the previous question, assume again that the server-pc network supports 100 hosts and the wifi supports 50 hosts.  Assume the following subnetting has been assigned to the **networks**:

1. Server-PC  192.168.1.128/25  

2. wifi  network 192.168.1.64/26 

3. Workstation-gateway point to point 192.168.1.8/30 

4. Server-PC router - gateway point to point 192.168.1.16/30 

5. Wifi router - gateway point to point network  192.168.32/30

  

  Suppose  an IP datagram arrives with destination address 192.168.1.67.  To which network or machine will the datagram go in your network?

Correct Answer:

Wifi network

**Explanation:**

If you look at the last bits:  

IP address is  0100 0011  

Wifi Network address (\26) is  01 | 0000, first two bits are part of the network address and zeroed out the rest.  You can see that the first 26 bits of the destination address matches the 26 bits of the network prefix for the wifi network.