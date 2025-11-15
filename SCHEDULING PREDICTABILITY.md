# SCHEDULING PREDICTABILITY

Predictability: the OS should guarantee that all critical timing constraints are met
Predictability requires _determinism_

Deterministic algorithm is an algorithm which, given a _particular input_, will always produce the _same output_, with the underlying machine always passing through the same sequence of states

And now we have seven source of nondeterminism

1. Direct memory access (DMA)
2. Cache memory
3. Interrupts
4. System calls
5. Semaphores
6. Memory management
7. Programming language

## Direct Memory Access (DMA)

DMA is used by many peripheral devices to transfer _data_ between the _device_ and the _main memory_

What is the mainly job of the DMA?

It relieves the CPU of the task of controlling the I/O transfer

The CPU and the I/O device share the same bus

The CPU is blocked when the DMA device is performing a data transfer

<br>

![alt text](attachments/section-6/dma.png)
_This diagram explains how Direct Memory Access (DMA) allows data to move between memory and an I/O device without the CPU copying the data itself._

| **Bus Type**    | **Purpose**                                                                  |
| --------------- | ---------------------------------------------------------------------------- |
| **Address Bus** | Selects the memory or I/O address (one-way: CPU → devices).                  |
| **Data Bus**    | Transfers data between CPU, memory, and I/O (two-way).                       |
| **Control Bus** | Sends control signals such as Read/Write, interrupts, and bus request/grant. |

DMA relieves the CPU from I/O management by sending a Bus Request to take control of the address, data, and control buses, receiving a Bus Grant from the CPU, and then directly transferring data between memory and I/O devices without CPU involvement in each read/write operation.

### DMA Data Transfer Modes

- **Burst Mode:** Transfers the whole block in one continuous operation; CPU is blocked for a long time.
- **Cycle Stealing:** DMA transfers one byte per bus request, then releases the bus; longer total transfer but shorter CPU blocking periods.
- **Transparent Mode:** DMA transfers only when the CPU is not using the buses, making DMA invisible to the CPU.

---

### DMA and Predictability

- DMA makes task response time **hard to predict** because the CPU can be blocked while DMA owns the buses.
- CPU blocking time depends on:
  - **Block size**
  - **DMA transfer mode**

### Real-time solution: **Time-sliced DMA**

- Each memory cycle is split into two slots (CPU + DMA).
- Slower, but **more predictable**.
- CPU and DMA never interfere.
- Task completion time is **independent** of DMA activity.

- **DMA is nondeterministic** because its bus usage and blocking duration vary with data size and system activity.
