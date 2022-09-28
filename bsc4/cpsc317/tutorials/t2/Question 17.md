**Question:**

Consider the following network diagram.  Suppose we assign the IP address of the workstation (on the point-to-point network with the gateway router) to be 192.168.3.68.  Would it be following convention for a point-to-point host to be configured this way on a /30 network? (Hint look at the host part).

Correct Answer:

False

**Explanation:**

Let's look at the last 8 bits. 

0100 0100, 

The host address is zero, which does not follow the convention that hosts ids cannot be all zeros or all ones.    I am ignoring that special RFC that allows you to configure point-point as a /31 because that is an exception to the rule.