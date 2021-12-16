# Enhanced xv6

For running-
> make clean 
> make qemu 
> 
## Tracing System Calls-

> strace runs the specified command until it exits, 
● It intercepts and records the system calls which are called by a process
during its execution.
● It should take one argument, an integer mask, whose bits specify which
system calls to trace.

Here We followed the hints provided under it.
- Added $U/_strace to UPROGS in Makefile
- Implemented sys_trace() function in kernel/sysproc.c.
- copied mask in fork in kernel/proc.c
- modified the syscall() function to print according to the syscall_name [made an array containing syscall_names also]
- made a user program in user/strace.c


---
## TASK 2

### FCFS SCHEDULING:
+ First in, first out (FIFO), is known as first come, first served (FCFS), is the simplest scheduling algorithm. 
+ FIFO simply queues processes in the order that they arrive in the ready queue.
+ No preemption is allowed.
+ In this, the process that comes first will be executed first and next process starts only after the previous gets fully executed.
+ To change the default scheduling to FCFS , run the make in the following way:

Run these commands:
> make clean 
> make qemu SCHEDULER=FCFS

---
### PRIORITY BASED SCHEDULING:
+ Priority scheduling is preemptive algorithm.
+ Each process is assigned priority. Process with highest priority (numerically least) is to be executed first and so on.
+ Processes with same priority are executed on first come first served basis.
+ If a process of higher priority(numerically less) arrives while a lower priority process is being executed the lower priority process is preempted.
+ To change the default scheduling to PBS , run the make in the following way: 

Run these commands:
> make clean qemu
> make qemu SCHEDULER=PBS

---

Performances-
1. for Rounrobin: wtime: 133, rtime : 17
2. for FCFS     : wtime: 87,  rtime : 49
3. for PBS      : wtime: 117, rime  : 21
---

