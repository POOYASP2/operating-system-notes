# Introduction to FreeRTOS

ok, when I write this, I tired as sag so may I have a lot issues in my writing and spelling.

## OUTLINE

- What is a Real-Time Application (RTA)?
- What is a Real-Time Operating System (RTOS)?
- RTOS vs General Purpose Operating System (GPOS)
- What is FreeRTOS?
- FreeRTOS kernel
- FreeRTOS configuration
- FreeRTOS demos
- First operations with FreeRTOS

### WHAT IS A REAL-TIME APPLICATION (RTA)

For a real time application we have new things which they are important too:

1. completion time
2. Predictability, the speed is not most important thing, the predictability is most important thing. We need a constant response time.

we have to type of the real time applications:

1. Hard real time
   - strict time deadline
   - missing the deadline cause catastrophic damages. (air bag)
2. Soft real time
   - time deadline
   - delay is tolerable (video streaming)

### WHAT IS A REAL-TIME OPERATING SYSTEM (RTOS)

- Operating system designed to reach time requirements
- Applications executed with very precise and deterministic timing

### RTOS vs General Purpose Operating System (GPOS)

| Real-Time Operating System (RTOS)                | General Purpose Operating System (GPOS)    |
| ------------------------------------------------ | ------------------------------------------ |
| Priority-based preemptive scheduling             | Scheduling for performance                 |
| Bounded interrupt and scheduling latency         | Unbounded interrupt and scheduling latency |
| Accepts lower throughput in favor of determinism | Maximizes throughput                       |
| Minimal kernel                                   | Larger kernel with more features           |

### What is FreeRTOS?
