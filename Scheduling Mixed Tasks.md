# Scheduling Mixed Tasks

In real application heterogeneous task sets are used (both periodic & aperiodic tasks)

Priority servers reserve execution capacity for aperiodic and sporadic tasks, improving their response times while ensuring periodic real-time tasks remain fully schedulable and protected.

## BACKGROUND SCHEDULING

1. Periodic tasks are scheduled using RM (rate monotonic scheduling)
2. Aperiodic tasks are scheduled in background, when no periodic instance is ready

### Characteristics of BACKGROUND SCHEDULING

Advantages:

1. Simple
2. Two ready queues are needed
   1. Periodic task queue: RM scheduling is used
   2. Aperiodic task queue: first-come-first-serve scheduling is used

Disadvantages:

1. In case of high periodic workload, response time for aperiodic tasks can be very high
2. Suitable only when aperiodic tasks are soft real-time

![alt text](attachments/section-6/BACKGROUNDSCHEDULING.png)
_BACKGROUND SCHEDULING_

## POLLING SERVER

Here we have a new terms, **SERVERS**. What is a server ?

A server is a special periodic tasks that created to server aperiodic tasks soon as possible.

Characteristics of a server

- Ts: period of the server
- Cs: capacity/budget of the server.

For Polling servers, it is scheduled using **RM** as other periodic tasks.

The main difference between a **POLLING SERVER** from a **DEFERRABLE SERVER** is a polling server consumes its budget either running an aperiodic task or immediately if no aperiodic tasks is ready.

The budget or capacity of a Polling Server is recharged at the beginning of each new period.

![alt text](attachments/section-6/polling-server-example.png)
_Example of Polling Server_
