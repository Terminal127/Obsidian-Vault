## Introduction to Distributed Operating Systems

Distributed is a collection of independent computers that work as a individual computers working together to solve a common problem and the user is unaware of the underlying architecture and these also share resources among themselves

### Goals

1. ***Advantages of Distributed System than Centralized system

So, basically buying cheap microprocessor is very cheap and is helpful in creating a cheap distributed system and also fault causes disruption in only one part of the system and also combining multiple cpus together to achieve a greater computation and also they provide room for growth like if we want to increase them later then we can do that too and also since they have multiple cpus so we have much faster speeds than Centralized system. [[1-chapter#Advantages of Distributed Systems over Centralized Systems]] 

2. ***Advantages of distributed system over independent PC

Here the thing is that in distributed we can utilize shared resources so that we have perfect sync and balance in loads which allows data sharing resource utilization and also we can make a symphony of shared and personal computers to do this and also this provided better person to person communication allowing better speed, flexibility and asynchronous compared to traditional methods. [[1-Chapter#Advantages of Distributed Systems over Independent PCs]]

***Disadvantages of Distributed OS

The primary disadvantage is that developing software based on distributed OS is really difficult because we don't have the we don't have a lot of experience regarding it and also there is network issue which is very troubled and can result in message loss and other problems which need recovery solutions and sometimes they are pretty expensive t o implement and also there is security risk of data getting stolen as it is easily accessible to people . [[1-Chapter#Disadvantages of Distributed Systems]]

### Hardware Concepts

  1. ***Bus based multiprocessors

In this type of architecture multiple cpus are connected to the memory through a single bus which means they all share a single bus and they have the **address data and control lines** which is the CPU used to read or write to memory and now the problem arises is that when multiple CPU like 5 or 6 are connected it creates congestion which basically slows it down a lot there fore high speed cache is used in this place so that the frequently used data can be stored in tit and in this way the hit rates can be increase by around 90 percent and now a problem is that if more than one CPU cache the same data and one updated which the other is not updated write through cache as it updates both cache and memory and also snoopy cache checks for changes and updated data when necessary. [[1-Chapter#Summary of Bus-Based Multiprocessors]]



   2. ***Switch based multiprocessors

The switch based multi processor used switches to connect cpus and memory instead of a single bus thus each CPU has a direct connection to the memory through a cross point switch thus multiple cpus can access the CPU together **which was not possible in the previous bus based connection** but the result was more complex and expensive setup ,There fore we had to use the omega Network which used switches (multiple 2 x 2 switches)
And the complexity was reduces but was still delay and latency. Therefore the NUMA architecture was born which basically used CPU has its won **local**  memory and the result was the fastest access time  but the time between accessing  other cpus memory was still slow [[1-Chapter#Summary of Switched Multiprocessors]]

3. ***Bus based multi-computers

The thing is that here each CPU has it own local memory and with no shared memory among them and the thing is that there is no cpu to memory connection among them and thus a high speed back-plane bus is necessary  and since the communication is cpu to cpu the communication is CPU to CPU there is very less interference among this. [[1-Chapter#^63bee4]]

4. ***switch based micro-computer

In this type of system the thing is that switch every cpu has access to its own private memory and there is a topology for this to work [[1-Chapter#^fb0ce1]]




