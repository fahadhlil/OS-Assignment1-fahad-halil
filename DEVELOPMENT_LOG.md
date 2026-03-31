# Development Log

## Instructions
Document your development process as you work on the assignment. Add entries showing:
- What you worked on
- Problems you encountered
- How you solved them
- Time spent

**Requirements**: Minimum 5 entries showing progression over time.

---

## Example Entry Format:

### Entry 1 - [April 1, 2026, 2:30 PM]
**What I did**: Forked the repository and set up my student ID

**Details**: 
- Created GitHub account with university email
- Forked the starter repository
- Changed student ID on line 92 to my actual ID (441234567)
- Compiled and ran the program successfully

**Challenges**: Had to install JDK first because javac wasn't recognized

**Solution**: Downloaded JDK 17 from Oracle website and set PATH variable

**Time spent**: 30 minutes

---

## Your Development Log:

### Entry 1 - [March 25, 2026, 4:10 PM]
**What I did**: Reviewed the assignment instructions and explored the starter code.

**Details**: 
- Read the assignment PDF carefully to understand the required tasks.
- Focused on Part 2 and Part 3 to know what code changes and documentation were expected.
- Opened `SchedulerSimulation.java` and read the `Process` class and the `main` method step by step.
- Identified how the ready queue works and how processes are re-enqueued in the Round-Robin cycle.

**Challenges**: 
At first, the code looked longer than expected because it included formatted output and progress bars, so it was not immediately easy to identify where the actual scheduling logic starts and ends.

**Solution**: 
I separated the code mentally into parts: process attributes, execution logic, scheduler loop, and queue helper method. This made it easier to understand the flow before making any modifications.

**Time spent**: 45 minutes

---

### Entry 2 - [March 26, 2026, 6:00 PM]
**What I did**: Updated my student ID and tested the original program before adding any features.

**Details**: 
- Replaced the default student ID in `SchedulerSimulation.java` with my own student ID.
- Ran the original program to observe the output and understand how the simulation behaves before any changes.
- Checked that the number of processes and the time quantum were generated correctly from the random seed.
- Took notes about how each process starts, yields the CPU, and finishes.

**Challenges**: 
I wanted to make sure that any future bug came from my new changes, not from misunderstanding the original code behavior.

**Solution**: 
I tested the original version first and used it as a baseline. This helped me compare the output before and after my modifications.

**Time spent**: 35 minutes

---

### Entry 3 - [March 27, 2026, 5:20 PM]
**What I did**: Implemented Feature 1 by adding process priority.

**Details**: 
- Added a new `priority` field to the `Process` class.
- Modified the constructor so each process receives a priority value when it is created.
- Generated random priorities from 1 to 5 in the `main` method.
- Updated the ready queue message so the priority of each process appears when it enters the queue.

**Challenges**: 
The main issue was making sure the new field was added without breaking the original constructor logic or the existing output messages.

**Solution**: 
I updated the constructor carefully, added a getter for priority, and tested the program after each small change. This helped me confirm that the feature worked while keeping the original scheduling logic unchanged.

**Time spent**: 50 minutes

---

### Entry 4 - [March 28, 2026, 7:15 PM]
**What I did**: Implemented Feature 2 to count context switches.

**Details**: 
- Added a static counter in `SchedulerSimulation` to track context switches.
- Incremented the counter each time a process started running.
- Also counted the final uninterrupted execution when the last process runs to completion.
- Printed the total number of context switches at the end of the simulation.

**Challenges**: 
I had to decide where a context switch should be counted in this specific simulation. I wanted the counting to reflect actual process starts, not random points in the loop.

**Solution**: 
I connected the counter to the moment just before a thread starts execution. I also included the final `runToCompletion()` case because it still represents a CPU handoff to a process.

**Time spent**: 40 minutes

---

### Entry 5 - [March 29, 2026, 3:45 PM]
**What I did**: Implemented Feature 3 to track waiting time for each process.

**Details**: 
- Added fields to track process creation time, last enqueue time, and total waiting time.
- Created methods to record when a process enters the ready queue and to update waiting time before execution.
- Stored completed processes in a separate collection for final reporting.
- Added a summary table at the end showing process name, burst time, and waiting time.

**Challenges**: 
This was the most difficult feature because waiting time is accumulated over multiple rounds in Round-Robin scheduling, not just once.

**Solution**: 
I used `System.currentTimeMillis()` and updated the waiting time every time the process left the queue and started execution. This allowed me to accumulate the total waiting time across the whole simulation.

**Time spent**: 1 hour 10 minutes

---

### Entry 6 - [March 30, 2026, 8:05 PM]
**What I did**: Reviewed the full program, tested the final output, and completed the documentation files.

**Details**: 
- Ran the updated program several times to verify that all three features were working correctly.
- Checked that the ready queue displayed priority, the context switch counter appeared at the end, and the waiting time summary table was printed correctly.
- Reviewed my code comments and made them clearer.
- Completed `DEVELOPMENT_LOG.md` and started writing reflective answers for `REFLECTION.md`.

**Challenges**: 
I wanted the final output to stay readable and consistent with the original code style while still showing the new information clearly.

**Solution**: 
I kept the new additions simple and avoided changing the original structure more than necessary. I also reviewed the assignment instructions again to make sure all required items were included.

**Time spent**: 55 minutes

---

## Summary

**Total time spent on assignment**: 4 hours 55 minutes

**Most challenging part**: Tracking waiting time correctly across multiple scheduling rounds.

**Most interesting learning**: Understanding how Round-Robin scheduling works together with thread execution and CPU handoff.

**What I would do differently next time**: I would plan the features on paper first and test each modification in even smaller steps before combining them.