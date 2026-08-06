# 💻 Module 26: Operating Systems (OS) Deadlocks & CPU Scheduling

Core Operating Systems concepts including Process vs Thread, 4 Deadlock Conditions, CPU Scheduling Algorithms, and Virtual Memory Paging required for exams and technical interviews.

---

## ⚡ 1. Process vs Thread Comparison

| Characteristic | Process | Thread |
| :--- | :--- | :--- |
| **Definition** | An executing program with isolated memory space. | Lightweight unit of execution inside a process. |
| **Memory Sharing** | Isolated virtual address space. | Shares code, data, and heap memory with other threads. |
| **Overhead** | High creation & context switching cost. | Low creation & fast context switching cost. |
| **Crash Impact** | If 1 process crashes, others continue running. | If 1 thread crashes, it may bring down the whole process. |

---

## 🔒 2. The 4 Necessary Conditions for Deadlock

A Deadlock can occur if and only if all four of the following conditions hold simultaneously:

1. **Mutual Exclusion:** At least one resource must be held in a non-shareable mode (only one process can use it at a time).
2. **Hold and Wait:** A process must be holding at least one resource and waiting to acquire additional resources held by other processes.
3. **No Preemption:** Resources cannot be forcibly taken away from a process; they can only be released voluntarily after completion.
4. **Circular Wait:** A closed chain of processes exists ($P_0, P_1, \dots, P_n$) such that $P_0$ waits for a resource held by $P_1$, and $P_n$ waits for a resource held by $P_0$.

---

## ⏱️ 3. CPU Scheduling Algorithms

- **FCFS (First-Come, First-Served):** Non-preemptive, suffers from Convoy Effect.
- **SJF (Shortest Job First):** Optimal minimum average waiting time; can cause Starvation for long tasks.
- **Round Robin (RR):** Preemptive scheduling using fixed Time Quantum / Time Slice $\tau$.
- **Priority Scheduling:** Preemptive or non-preemptive; solved via Aging technique (gradually increasing priority of waiting processes).
