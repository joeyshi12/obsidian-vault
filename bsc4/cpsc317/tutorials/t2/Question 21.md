**Question:**

As a challenge, assuming the hosts as shown in the network diagram (e.g. 4 hosts on the PC-server network and 3 hosts on the Wifi network).  Can you successfully assign subnets if all you are allocated is the block 192.168.0.0/28? Hint: might not be possible, if not, explain why).

Correct Answer:

False

**Explanation:**

Looking at the last 4 four bits  use a /29 server-pc network, (give you $8-2$ hosts), use /30 which gives you $4-2$ hosts, not enought to number the hosts of the wifi network.  Can't be done

  

Might be possible with /27, but you going to have to pull out the exception with a /31 to do it.  /26 is easy.