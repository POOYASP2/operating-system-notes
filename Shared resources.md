# Shared resources

**Q -** what is resource?

> any software structure used by **processes** to **advance** its **execution** like Data structure, set of variables, main memory area, file, set of registers of a peripheral device

We have two types of the resources:

1. Private resource (a resource dedicated to a particular process)
2. Shared resource (a resource that can be used by more tasks)
   1.Shared exclusive resource (a shared resource protected against concurrent accesses that means only one process at a time can use the resource)

## Race problem

![alt text](attachments/section-6/Race-problem.png)

Actually, the `count++` process is not a single instruction for CPU.
May in the middle of that operation the CPU preempts the process and run other instructions and our shared resource changed in this preemption. So we must a solution for race problem. the lecturer presents these solutions:

1. Disabling the interrupts
2. SPINLOCK — BUSY WAITING
3. Semaphores

So now, we explain each of these solutions.

### Disabling the interrupts

The race problem happens when CPU preempts a task with a interrupt, if we disable it the instructions of the task run together.

Advantages:

- simple

Disadvantages:

- Interrupt latency not predictable → bad for real time
- Disable preemption may prevent scheduling of higher priority independent tasks.

### SPINLOCK — BUSY WAITING

![alt text](<attachments/section-6/SPINLOCK — BUSY WAITING.png>)

Allows a thread to "spin" (actively wait) until it acquires a lock.

Typically used in multiprocessor systems where waiting is expected to be brief

Advantages:

- Simple and fast for short waits
- No context switching overhead

Disadvantages:

- Wastes CPU cycles while waiting (busy-waiting)
- Not ideal for single-processor systems
