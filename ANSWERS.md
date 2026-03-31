# Assignment Questions

## Instructions
Answer all 4 questions with detailed explanations. Each answer should be **3-5 sentences minimum** and demonstrate your understanding of the concepts.

---

## Question 1: Thread vs Process

**Question**: Explain the difference between a **thread** and a **process**. Why did we use threads in this assignment instead of creating separate processes?

**Your Answer:**

A process is an independent program in execution that has its own memory space and system resources, while a thread is a smaller unit of execution that exists within a process and shares its memory. One key difference is that processes do not share memory by default, which makes communication between them more complex and slower. In contrast, threads share the same memory space, which makes communication faster and more efficient. Another important difference is that creating a new process is more expensive in terms of system resources, while creating threads is lightweight and faster. In this assignment, threads were used because all simulated processes run within the same program and need to be scheduled efficiently. Using threads allowed us to simulate CPU scheduling behavior without the overhead of managing separate processes.

---

## Question 2: Ready Queue Behavior

**Question**: In Round-Robin scheduling, what happens when a process doesn't finish within its time quantum? Explain using an example from your program output.

**Your Answer:**

In Round-Robin scheduling, if a process does not finish within its allocated time quantum, it is paused and placed back at the end of the ready queue. This allows other processes to get a fair share of CPU time instead of one process using all the resources. The process will eventually get another chance to run when it reaches the front of the queue again. This behavior ensures fairness and prevents starvation.

Example from my output: