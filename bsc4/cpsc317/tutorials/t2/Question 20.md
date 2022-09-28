**Question:**

Using the same network diagram, assume again that the server-pc network supports 100 hosts and the wifi supports 50 hosts. Suppose the  **workstation** is assigned CIDR address 192.168.1.69/30.  Which of the following is a possible network prefix of the **server-pc network**? (only the network bits are shown).  Assume for this question that you can freely assign networks from the 192.168/16 block.  Given the workstation address, consider possible network addresses for the server-pc. 

Correct Answer:

11000000 10101000 00000001 1

**Explanation:**

Again the last 8 bits is 0100 0101 and 30 of these bits are used for the point-to-point network. Consider each of the answers

A. is okay it works using this as a /25. It fits and differs from the workstation network (i.e. host blocks do not overlap).

B. /26 is too small (only leaves 64 hosts)

C. Conflicts with the /30 network (the last few network bits are, the first 25 bits match the workstation network address. There is overlap.

D. This is the network prefix of a network with only 1 host, it is the host (self).  Sometimes used as a loopback in network devices (these are all corner cases that may vary depending on the equipment).  No other host-id can be assigned.

E. Oops the first byte is different, not even in this network at all.