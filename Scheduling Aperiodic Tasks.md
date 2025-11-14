# Scheduling Aperiodic Tasks

What is an aperiodic task?  
An aperiodic task is a task that has an infinite sequence of identical instances whose activations are not regularly interleaved.
A scheduling algorithm defined using α|β|γ

**α** describes the machine environment on which the task set must be scheduled (uniprocessor, multiprocessor, distributed architecture, and so on)

**β** describes task and resource characteristics (preemptive, synchronous activations, and so on)

**γ** indicates the optimality criterion (performance measure) to be followed in the schedule

![alt text](attachments/section-6/image.png)
_An example of an algorithm for an aperiodic task_

## What are the aperiodic tasks scheduling algorithms?

### JACKSON’S ALGORITHM 1 | sync | Lmax

Numbers of processors: 1

Arriving time of the tasks: synchronous

Objective of the algorithm: minimize the maximum lateness

Preemption: None-preemptive

The main idea: EDD => Earliest Due Date

![alt text](attachments/section-6/example1.png)
_Example one for JACKSON's algorithm_

**Lmax** is the maximum lateness of all jobs, computed as the largest value of

$$
L\_{\max} = \max (f_i - d_i)
$$

So in this example we have another **Lmax**

![alt text](image.png)
_Example two for JACKSON's algorithm_
