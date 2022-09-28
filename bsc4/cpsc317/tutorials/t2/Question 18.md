**Question:**

Consider the following network (same as given previously).  Let us now  assume that we have only been allocated a 192.168.1.0/24 block of address to use for our subnetting.

  

Furthermore let's assume that the Server-PC network (the one on the lower left-hand side of the diagram) needs to support **at  least 100** hosts and the wifi network needs to support **at least 50**  hosts.   

  

Which of the following network prefixes did you use?  Use a prefix which is the right size (e.g. big enough but as close as possible)  for the given networks.  (i.e. use the right size for point-to-point).

Correct Answers

/25

/26

/30 or /31

**Explanation:**

We need to assign network bits to the four networks.  

  

The following works.

1. Server-PC  192.168.1.128/25  (last bits 1xxx xxxx) supporting 126 hosts

2. wifi  192.168.1.64/26 (last bits 01xx xxxx) supporting 62 hosts

3. one point-to-point 192.168.1.4/30 (last bits 0000 01xx)

4. second point-to-point 192.168.1.8/30 (last bits 0000 10xx)

  

Note for the point-to-point you could have used /27 or /28 or /29 but point-to-point links are typically /30 or /31.  Either /30 or /31 is the appropriate size.