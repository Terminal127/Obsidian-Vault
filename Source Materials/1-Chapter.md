
### Advantages of Distributed Systems over Centralized Systems


1. **Economics**: Distributed systems provide a better price/performance ratio than mainframes. Microprocessors are cheaper, and by combining multiple CPUs, you can achieve greater computing power at a lower cost.

2. **Speed**: Distributed systems can harness the power of multiple processors, offering total computing power that exceeds what a single mainframe can achieve.

3. **Inherent Distribution**: Some applications are naturally distributed, such as supermarket chains or cooperative work environments, where local processing is more efficient.

4. **Reliability**: In a distributed system, the failure of a single machine only affects a portion of the system, allowing the rest to continue functioning with minimal performance loss. ^694ef1
7. **Incremental Growth**: Distributed systems allow for gradual expansion by adding more processors as needed, avoiding the disruption of replacing or adding entire mainframes.

Overall, distributed systems offer advantages in cost, performance, reliability, scalability, and support for inherently distributed applications.


### Advantages of Distributed Systems over Independent PCs

1. **Data Sharing**: In many applications, such as airline reservations, users need to share data. Distributed systems allow for shared access to data, ensuring consistency and avoiding conflicts that would arise from isolated systems.

2. **Shared Resources**: Expensive peripherals like color laser printers and large storage devices can be shared across multiple users in a distributed system, making resource utilization more efficient.

3. **Enhanced Communication**: Distributed systems enable better person-to-person communication through tools like email, which offers speed, flexibility, and asynchronous communication compared to traditional methods like paper mail, phone, and fax.

4. **Flexibility and Load Balancing**: Distributed systems allow for a mix of personal and shared computers, enabling jobs to run on the most suitable machines. This leads to better load distribution and resilience against the failure of individual machines.

Overall, distributed systems provide essential data sharing, resource sharing, enhanced communication, and greater flexibility compared to independent PCs.

### Disadvantages of Distributed Systems

1. **Software Challenges**: Developing, implementing, and using distributed software is complex. The current state of software for distributed systems is limited, and there is still much uncertainty about the best practices for designing operating systems, programming languages, and applications for these systems. This lack of experience makes it difficult to optimize distributed systems effectively.

2. **Networking Issues**: The communication network in a distributed system can encounter problems such as message loss, requiring additional software for recovery. Networks can also become overloaded, leading to performance bottlenecks. In cases of network saturation, expensive upgrades, rewiring, or the addition of new networks may be necessary, potentially negating the benefits of the distributed system.

3. **Security Concerns**: While distributed systems offer convenient data sharing, they can also pose security risks. Unauthorized access to sensitive data becomes easier, potentially compromising the confidentiality of critical information. In some cases, it may be safer to use isolated, non-networked computers for highly sensitive data.

Despite these drawbacks, the advantages of distributed systems often outweigh the disadvantages, and their use is expected to grow in the coming years.

### Summary of Bus-Based Multiprocessors

Bus-based multiprocessors connect multiple CPUs to a shared memory via a common bus. The bus typically has address, data, and control lines operating in parallel. When a CPU wants to read or write memory, it uses the bus to send signals, and the memory responds accordingly. This setup ensures memory coherence, meaning that changes made by one CPU are visible to others.

However, as the number of CPUs increases (around 4 or 5), the bus can become overloaded, leading to performance drops. To solve this, high-speed cache memory is added between each CPU and the bus. The cache stores frequently accessed data, reducing bus traffic when data is already in the cache. This approach improves performance by achieving high hit rates (up to 90%).

The introduction of caches, however, can create coherence problems. If two CPUs cache the same data and one updates it, the other may still have the old data. To address this, **write-through caches** are used, which write data to both the cache and main memory simultaneously. Additionally, **snoopy caches** monitor the bus for changes and update their data when necessary, ensuring coherence. This design allows systems to support 32 to 64 CPU s on a single bus.

![[Pasted image 20240831184603.png]]


### Summary of Switched Multiprocessors

Switched multiprocessors connect many CPUs to memory using switching networks rather than a single bus. For systems with more than 64 CPUs, alternative methods are needed:

1. **Crossbar Switches**: This method uses a matrix of switches to connect CPUs with memory modules. Each CPU and memory has a direct connection via a crosspoint switch. The advantage is that multiple CPUs can access memory simultaneously. However, the major downside is the high cost and complexity due to the need for a large number of switches, which grows exponentially with the number of CPUs and memory modules.

2. **Omega Network**: An alternative to the crossbar switch is the omega network, which uses fewer switches. It consists of multiple stages of 2x2 switches that can route data between CPUs and memories. Although the omega network is more efficient in terms of the number of switches required (logarithmic rather than exponential), it still faces issues with delay. For example, a large number of switching stages can add significant latency to memory access times.

3. **NUMA (Non-Uniform Memory Access)**: To reduce costs and delays, hierarchical systems like NUMA are used. In a NUMA machine, each CPU has its own local memory, which can be accessed quickly, while accessing other CPUs' memories is slower. This approach improves average access times but introduces complexity in software placement to ensure data is stored in the most accessible memory.

In summary, while bus-based multiprocessors are limited in scalability, switched networks like crossbars and omega networks provide solutions for larger systems but come with their own challenges, including high cost and increased latency. NUMA machines offer a compromise by combining local memory access with hierarchical memory access but require careful management of data placement.

![[Pasted image 20240831200309.png]]

### Summary of Multi computers

**1.3.3. Bus-Based Multi computers** ^63bee4

- **Architecture**: Each CPU in a bus-based multi computer has its own local memory and communicates with other CPUs through a shared network. Unlike bus-based multiprocessors, there's no shared memory, so the network traffic primarily involves CPU-to-CPU communication.
  
- **Network**: This network can be a low-speed LAN (10-100 Mbps) instead of a high-speed bus, making it suitable for workstations connected over a local network. The reduced traffic load allows for simpler, lower-speed interconnection compared to multiprocessors.

- **Configuration**: It often consists of workstations connected over a network rather than a high-speed bus-based system.

![[Pasted image 20240831223602.png]]


**1.3.4. Switched Multicomputers** ^fb0ce1

- **Architecture**: Switched multicomputers use various interconnection networks where each CPU has direct access to its own private memory. This setup allows for scalable and flexible configurations.

- **Topologies**:
  - **Grid**: A grid topology arranges CPUs in a two-dimensional layout, making it straightforward to design and implement. It's ideal for problems with a two-dimensional nature, such as graph theory and image processing.
  
  - **Hypercube**: A hypercube is an n-dimensional structure where each CPU has connections to n other CPUs. The complexity of wiring grows logarithmically with the number of CPUs, which helps maintain manageable path lengths for data transfer. Hypercubes can have thousands of CPUs, with commercially available systems reaching up to 16,384 CPUs.


![[Pasted image 20240831223630.png]]

In summary, multi computers offer flexibility with each CPU having private memory and various interconnection options, including simpler LAN setups or complex hypercube structures.


