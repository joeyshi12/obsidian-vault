---
course: CPSC317
title: M6 Learning Goals
topic: Learning Goals
tags:
module: 6
date: [[2022-11-07]]
---

**A.  Communicating State Machines**
-  Given a protocol express it as a set of communicating finite state machines
-  Given a set of communicating finite state machines trace the execution of the protocol for various event scenarios
-  Given a set of communicating finite state machines analyze the execution of the state machines to determine whether or not the protocol operates correctly and propose ways to solve any problems

**B.  Reliable Data Transfer**
-  Describe/build/execute/trace the various versions of the alternating bit protocol (stop and wait) protocol
-  Explain how corruption in packets are detected and at what layer(s) in the protocol stack this is done
-  Understand the role of ACK/NACK, sequence numbers and timeouts in building a reliable delivery protocol
-  Explain the role of timeouts in building a reliable delivery protocol
-  Understand the affect of time-out on performance and for a given scenario determine an appropriate time-out value.
-  Understand the relationship  of the number of sequence numbers to window sizes and out-of-order packets
-  Trace the execution of GBN and SR when the range of sequence numbers is restricted
-  Determine window sizes to maximize link utilization
-  Argue why a sliding window protocol is needed
-  Trace the execution of GBN and SR
-  Analyze GBN and SR under packet loss

**C. TCP**
-  Know and understand the purpose of the major fields in the TCP header
-  Understand how a sliding window protocol is used in TCP.
-  Understand the importance of estimating RTT and using it to set the time-out values.
-  Explain how a timeout value is determined and the things like jitter and varying RTTs are accommodated.
-  Understand how TCP's sliding window is used for flow control, i.e. advertised window size.
-  Describe  how the receiver can control how much data the sender can send before pausing and waiting for buffers to empty
-  Understand TCP's connection management for initiating and terminating connections.
-  Understand what causes congestion and how it is detected by TCP.
-  Explain how the sending process can detect congestion
-  Describe and analyze strategies for controlling the sending window size with respect to congestion
-  Describe and analyze strategies for how the receiver can control how much data the sender can send before pausing and waiting for buffers to empty`