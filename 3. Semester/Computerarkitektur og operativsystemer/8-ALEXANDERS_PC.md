### Recap
![[Pasted image 20251107093046.png]]
Real-time CPU scheduling and algorithm evaluation will be introduced in lecture 9 instead.

### Multithreaded programming
![[Pasted image 20251107093130.png]]
They need their own registers, stack and PC, because they have different operations to execute simultaneously.
### Multithreaded server
![[Pasted image 20251107093331 1.png]]
Pros:
- Responsiveness.
- Resource Sharing.
- Economy.
- Scalability.
### Concurrency v.s. Parallelism
![[Pasted image 20251107093543 1.png]]
### Two types of parallelism
![[Pasted image 20251107093850 1.png]]
Data parallelism: you distribute the data over several cores
Task parallelism: you distribute the tasks, so each core does a different operation.
### Amdahl's law
![[Pasted image 20251107094037 1.png]]
$$
\text{speedup} \leq \frac{1}{S + \frac{1-S}{N}}
$$
Cons:
Find tasks that can be performed in parallel. The tasks need to take the same amount of time to complete. The data needs to be able to be split. You might have to wait for the output of something to use it as input for another task. Hard to test and debug.
### Multithreading models
#### Many-to-one
![[Pasted image 20251107094603 1.png]]
Keep in mind both of the threads are software threads, and the user only has access to the user threads.
#### One-to-one
![[Pasted image 20251107094752 1.png]]
#### Many-to-many
![[Pasted image 20251107094817 1.png]]
Keep in mind the amount of kernel threads are usually less than the user threads.
#### Two-level-model
![[Pasted image 20251107094826.png]]
The kernel threads are like middleware that keeps track of all of the low level things, like when using a joystick to control a robot arm, ROS will make sure the arm moves stable and so on while completing the high-level task.

#### Example: Solaris two-level model
![[Pasted image 20251107095459.png]]
### CPU scheduling
![[Pasted image 20251107095513.png]]
### CPU-burst histogram
![[Pasted image 20251107095550.png]]
### Scheduling parameters (design objectives)
![[Pasted image 20251107095607.png]]
### FCFS scheduling
![[Pasted image 20251107100906.png]]
### Convoy effect
![[Pasted image 20251107101001.png]]
### SJF (Shortest-Job-First) scheduling
![[Pasted image 20251107101015.png]]
![[Pasted image 20251107101035.png]]
#### Preemptive v.s. non-preemptive scheduling
When scheduling is preemptive it means if it receives a shorter task after it started a long task, it will switch to the shorter task instead of sticking with the task it is doing at the moment, so it always checks for shorter tasks to switch to.
### Prediction of scheduling time
![[Pasted image 20251107101046.png]]
It's a prediction based on an algorithm that checks the current measured burst time, where the closer it is to present time the higher weight it has, because it is more recent. Its essentially just an exponential average filter.
$\alpha$ is a weight, so if $\alpha$ is 1 then you only rely on the most recent measurement and ignore the rest, if its 0 then you ignore the most recent measurement and only use the historical data, usually you just use $0.5$ if you don't have a good idea. 
### RR (Round-Robin)
![[Pasted image 20251107103001.png]]
### Size of time slice effect on context switches
![[Pasted image 20251107103302.png]]
### Priority scheduling
![[Pasted image 20251107103319.png]]
### Priority scheduling with Round-Robin
![[Pasted image 20251107103443.png]]
### Multilevel queue scheduling
![[Pasted image 20251107103544.png]]
### Multilevel feedback queue scheduling
![[Pasted image 20251107103807.png]]
It uses a reward/punish system where if a task takes a long time it will get a lower priority in the queue, if a task has waited a long time it will move up to a higher priority queue.
### Multi-processor scheduling
![[Pasted image 20251107104244.png]]
- Asymmetric multiprocessing - Here it is a processor that does the scheduling, I/O processing, etc., i.e., system administration. Other processors are responsible for only user code

- Symmetric multiprocessing (SMP) - Each processor is self-scheduling but can either have a common ready queue or its own private ready queue. To achieve balanced workload in such systems, two approaches can be used:
	- Push migration - here an administrative process periodically checks the load on each processor and evenly distribute the load by moving or pushing threads from overloaded to idle processors.
	- Pull migration - here idle processors pull processes from the ready queues of busy processors. combination of both strategies often occurs in real systems

- Processor Affinity - a process has an affinity for the processor on which it is currently running, as it is costly to move it to another processor (due to cache, etc.).
	- Soft connection – here you try to keep the process on a processor, but no guarantee.
	- Hard connection – here the process is guaranteed to run on the designated processor.
	- A variant allows the process to specify a set of processors on which it can run.

### SMP (multi-processor scheduling)
![[Pasted image 20251107104638.png]]
### Memory stall
![[Pasted image 20251107104641.png]]
Simultaneous multithreading allows a single physical processor core to maintain the architectural state of multiple threads and interleave their execution. When one thread encounters a stall condition (memory access, branch misprediction, etc.), the processor can immediately switch to executing instructions from another thread without context switching overhead, making better use of the execution resources that would otherwise sit idle. This will from the OS look like you actually have two physical cores and it will use them accordingly.
### Multithread multicore system
![[Pasted image 20251107104924.png]]
### Two levels of scheduling
![[Pasted image 20251107105054 1.png]]
There are basically three, if you also count the user interface and kernel interface as a level as well.
![[Pasted image 20251107103807.png]]