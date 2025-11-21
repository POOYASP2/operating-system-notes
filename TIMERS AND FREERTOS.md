# TIMERS AND FREERTOS

## TL;DR

Timers in general are hardware counters. In FreeRTOS, software timers are built on top of the single system tick timer. Instead of each timer being its own task, FreeRTOS uses a single Timer Service Task to manage a list of multiple software timers, allowing us to trigger many periodic events using only one hardware source.

## OUTLINE

1. Hardware Timer Basics

2. Clock Sources and Prescalers
3. The FreeRTOS Tick
4. Approaches to Periodic Operations
5. FreeRTOS Software Timers
6. Software Timer Architecture (Daemon Task)
7. Timer Implementation and Code

---

## 1 - Hardware Timer Basics
