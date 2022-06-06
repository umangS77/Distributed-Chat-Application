# Distributed chat application

## Overview
The purpose of this project is to design a distributed chat application and to provide users with an instant messaging tool that has the ability to handle multiples of users simultaneously when needed and can be easily done. 

## Goals
- The system should be highly scalable : Multiple clients and servers should be able to work together in the distributed system.
- It should be fault-tolerant : The system should be up and running, even if one or multiple servers crash.


## Execution
- run server.py files on different systems which will be used as servers.
- run client.py files on different systems which will be used as clients.

## Brief Explanation about the algorithms used

### Fault Tolerance

A faulty system creates a human/economic loss, air and rail traffic control, telecommunication loss, etc. The need for a reliable fault tolerance mechanism reduces these risks to a minimum. In distributed systems, faults or failures are limited or part. A part failure in distributed systems is not equally critical because the entire system would not be offline or brought down, for example a system having more than one processing cores (CPU), and if one of the cores fails the system would not stop functioning as though that’s the one physical core in the system. Hence, the other cores would continue to function and process data normally. Nevertheless, in a non-distributed system when one of its components stops functioning, it would lead to a malfunction of the entire system or program and the corresponding processes would stop.  
Fault tolerance is the dynamic method that’s used to keep the interconnected systems together, sustain reliability, and availability in distributed systems. The hardware and software redundancy methods are the known techniques of fault tolerance in distributed systems. The hardware methods ensure the addition of some hardware components such as CPUs, communication links, memory, and I/O devices while in the software fault tolerance method, specific programs are included to deal with faults. Efficient fault tolerance mechanism helps in detecting faults and if possible recovers from it.There are various definitions to what fault tolerance is. In dealing with fault tolerance, replication is typically used for general fault tolerance method to protect against system failure


### Dynamic discovery of hosts

Here is some scenario:  
Hosts: A, B, C, D, E, F, G  
Your application knows only node (server) A. So your application asks A to join the net. And after A verifies your application to be allowed to and able tojoin the net tells your application all about B, C, D, E, F, G. Also the server Atells all the other nodes about your application joining the net. After thissimple routine all hosts know about your application and your applicationknows about all the hosts.  

Now lets say Bobs application is also joinging the network asking sever E to
join. Bobs application learns all about the other hosts A, B, C, D, F, G. And E
tells Bobs application about your application. But then there is this message
(or event) distribution system your application listens to and E just publish a
message that Bobs application joined. Since your application listens to this
kind of messages your application learns that Bobs application has also
joined.  
After some time server D crashed. Since the hosts A, B, C, E, F, G constantly
listens to messages of D they notice that D is not sending any messages any
more. So they send messages telling everyone listening that D has left the
network. After a short periode D recovered and rejoined the network.  
Thats basically all that is important about dynamic discovery of hosts. There
are a bunch (at least one) of servers, you only know one or more (at least 3
are mostly recommanded if one has crashed and is recovering) and asks to
join and to get some more information about other hosts. Then your
application listens to status informations or is requesting one of the server to
keep your application informed about the events of joining and leaving of
servers from the logical network.  

### Voting and Leader election

The objective of leader election is to provide one item (a process, host,
thread, object, or human) specific powers in a distributed system. These
specific abilities could include the capacity to delegate tasks, the ability to
edit data, or even the responsibility for managing all system requests.  
The election of a new leader is a powerful instrument for increasing
efficiency, minimizing coordination, simplifying architectures, and lowering
activities. Leader election, on the other hand, may generate additional failure
modes and scale obstacles. Furthermore, leader election may make
evaluating the validity of a system more challenging.  
The goal of the leader election is to select a processor who will coordinate
the system’s actions. A leader is usually chosen based on a criterion, such as10
selecting the processor with the greatest identifier as the leader in any leader
election procedure. The processors attain their terminated states when the
leader is chosen. In a leader election algorithm, the terminated states are
divided into elected and non-elected states. When a processor enters a
non-elected state (or an elected state), it remains in that state at all times (or
an elected state).  

### Heartbeat mechanism

In distributed systems, a heartbeat is a periodic signal generated by
hardware or software to indicate normal operation or to synchronize other
parts of a computer system. Heartbeat mechanism is one of the common
techniques in mission critical systems for providing high availability and fault
tolerance of network services by detecting the network or systems failures of
nodes or daemons which belongs to a network cluster—administered by a
master server—for the purpose of automatic adaptation and rebalancing of
the system by using the remaining redundant nodes on the cluster to take
over the load of failed nodes for providing constant services. Usually a
heartbeat is sent between machines at a regular interval in the order of
seconds; a heartbeat message. If the endpoint does not receive a heartbeat
for a time—usually a few heartbeat intervals—the machine that should have
sent the heartbeat is assumed to have failed. Heartbeat messages are
typically sent non-stop on a periodic or recurring basis from the originator's
start-up until the originator's shutdown. When the destination identifies a
lack of heartbeat messages during an anticipated arrival period, the
destination may determine that the originator has failed, shutdown, or is
generally no longer available.


### Multicast

Communication between two processes in a distributed system is required to
exchange various data, such as code or a file, between the processes. When
one source process tries to communicate with multiple processes at once, it
is called Group Communication. A group is a collection of interconnected
processes with abstraction. This abstraction is to hide the message passing
so that the communication looks like a normal procedure call. Group
communication also helps the processes from different hosts to work
together and perform operations in a synchronized manner, therefore
increases the overall performance of the system.  
When the host process tries to communicate with a designated group of
processes in a distributed system at the same time. This technique is mainly
used to find a way to address problem of a high workload on host system
and redundant information from process in system. Multitasking can
significantly decrease time taken for message handling.

## Demo
https://drive.google.com/drive/folders/1FbSGiwZTE8skRIXrOl5aQfs4AEqsk_x6?usp=sharing