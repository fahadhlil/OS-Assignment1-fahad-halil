# Reflection Questions

## Instructions
Answer the following questions about your learning experience. Each answer should be **at least 5-7 sentences** and show your understanding.

---

## Question 1: What did you learn about multithreading?

**Your Answer:**

This assignment helped me understand multithreading in a much more practical way than just reading theory. I learned that a thread is a lightweight unit of execution that allows multiple tasks to make progress within the same program. In this simulation, each process was represented using a Java thread, which made the scheduling behavior easier to visualize. I also learned that threads do not just “run automatically”; they move through different states depending on how the program controls them. For example, a thread starts when `Thread.start()` is called, and the main scheduler waits for it using `Thread.join()`. I noticed that thread coordination is very important because the program must control when one process runs and when another one gets its turn. Overall, this assignment made me connect thread creation, execution, waiting, and termination to actual program behavior instead of seeing them as abstract concepts.

---

## Question 2: What was the most challenging part of this assignment?

**Your Answer:**

The most challenging part of this assignment was tracking the waiting time for each process correctly. At first, I thought waiting time could be measured once when the process was created, but I realized that this is not accurate in a Round-Robin scheduler. A process may run for one quantum, return to the ready queue, and then wait again before its next turn. This means the waiting time must be accumulated over several cycles, not calculated only once. Another challenge was understanding exactly where to place the timing logic without affecting the original behavior of the program. I also had to be careful not to confuse execution time with waiting time. In the end, this feature was difficult because it required both understanding the scheduling algorithm and translating that understanding into code.

---

## Question 3: How did you overcome the challenges you faced?

**Your Answer:**

I overcame the challenges by breaking the problem into smaller steps and testing each step separately. First, I studied the original code carefully before adding any new features so I could understand how the scheduler loop worked. Then I focused on one feature at a time instead of trying to implement everything at once. For the waiting time problem, I followed the actual process lifecycle and identified the exact moments when a process enters the ready queue and when it starts running again. After that, I used `System.currentTimeMillis()` to measure those intervals and accumulate them gradually. I also checked the output after every modification to make sure the program still behaved correctly. This approach helped me avoid large mistakes and made debugging much easier.

---

## Question 4: How can you apply multithreading concepts in real-world applications?

**Your Answer:**

Multithreading concepts are very useful in many real-world applications because modern software often needs to handle multiple tasks at the same time. One example is a web server, where multiple client requests may arrive concurrently and each request can be handled by a separate thread. Another example is a media player, where one thread can handle audio playback while another thread updates the user interface and another reads data from storage. These tasks need to happen smoothly without making the program feel frozen or slow. The idea of scheduling is also important in such systems because CPU time must be shared fairly and efficiently between active tasks. This assignment showed me how threads can be managed in a controlled way using a scheduler-like structure. It also made me understand why fairness, responsiveness, and coordination are important in practical software systems.

---

## Additional Reflections (Optional)

### What would you like to learn more about?

I would like to learn more about synchronization and race conditions because this assignment mainly focused on scheduling and thread execution order. I know that in more advanced multithreaded programs, threads often share data, which can create consistency problems if access is not controlled properly. I am especially interested in learning how `synchronized`, locks, and semaphores are used in Java and operating systems. I also want to understand deadlocks more deeply and how operating systems prevent or detect them. Another topic I would like to study is the difference between user-level threads and kernel-level threads. I think learning these topics would help me move from basic multithreading concepts to more advanced concurrency problems.

---

### How confident do you feel about multithreading concepts now?

Intermediate

I feel more confident than before starting this assignment because I now understand thread creation, scheduling flow, and the basic lifecycle of a thread in practice. I can follow how a thread moves from being created to being started, executed, waited on, and terminated. I also understand the role of `Thread.start()`, `Thread.join()`, and timed execution in a simulation like this one. However, I still think I need more practice with advanced topics such as synchronization, shared memory issues, and thread safety. So I would describe myself as intermediate rather than fully confident. I understand the foundations, but I still need more experience with more complex multithreaded systems.

---

### Feedback on the assignment

I think this assignment was useful because it connected operating systems theory with actual Java code. It was more meaningful than just answering theoretical questions because it required understanding and modifying a working simulation. The three added features were also well chosen because they made me think about scheduling behavior more deeply. The waiting time feature in particular helped me understand how process scheduling metrics are calculated over time. I also liked that the assignment included reflection and documentation because it encouraged careful thinking instead of only coding. The only difficult part was that the starter code had a lot of formatted output, which made the logic a little harder to follow at first. Overall, I think the assignment was challenging in a good way and helped me learn practical multithreading concepts.