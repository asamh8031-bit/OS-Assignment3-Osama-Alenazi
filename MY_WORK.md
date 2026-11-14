# 📝 MY_WORK: Student Information, Development Log, Reflection & Answers

> This is the **only file** your instructor reads to grade Parts 3 and 4 (documentation and video). Everything you write here must be **in your own words**.

---

## 🛑 STOP: Read This Before You Do Anything Else

> ### 1️⃣ Read the whole `README.md` first
> The `README.md` in this repository contains the full instructions: how this assignment continues Assignment 1, the Chapter 5 recap, class descriptions, feature specifications, question prompts and the video script. **If you skip it, you will lose marks.**
>
> ### 2️⃣ Understand the full code before answering any question
> Open `SchedulerSimulationSync.java` and read it **from top to bottom**. You must be able to explain what `SharedStats`, `ReadyQueue`, `CpuWorker`, `RaceWindow.pause()`, `ReentrantLock` and `Semaphore` do **before** you write a single answer in Parts B and C. **Run the original starter first** (it is intentionally broken) and **save its output**: you need it for Question 1 of Part C.
>
> ### 3️⃣ Use only the code of this repository
> Work **only** on `SchedulerSimulationSync.java` from this repository. Do **not** copy or paste code from your previous assignments.
>
> ### 4️⃣ Commit many times, not once
> A single commit, or all commits made in the last hour, costs you **-0.5 mark**. See the [Commit Rules](#-commit-rules-mandatory) below.

**How to use this file:**
1. Fill in your **Student Information** (below) right now.
2. Follow the steps in the **Work Roadmap** in order.
3. Update the **Development Log** *every time* you work on the assignment, not at the end.
4. Do not delete any section header. Replace the `[...]` placeholders with your own text.

---

## 👤 Student Information

> ⚠️ **WARNING:** Fill this in first. Your name and ID must match the student ID you set in `SchedulerSimulationSync.java` (line 304) and the one you say in your video.

| Field | Your Answer |
|-------|-------------|
| **Full Name** | [Write your full name here] |
| **Student ID** | [Write your student ID here] |
| **University Email** | [yourid]@std.psau.edu.sa |
| **GitHub Username** | [your-github-username] |
| **Repository Link** | [Paste your repository link here] |
 
---

## 🎥 Video Link

**Video Link**: [Paste your video link here]

> ⚠️ **WARNING:** The video must be **publicly accessible** ("Anyone with the link can view") on **Google Drive**, **YouTube (Unlisted or Public)** or any other cloud file-sharing system. A private, restricted or broken link counts as a **missing video (-1 mark)**.
>
> 💡 **TIP:** Open the link in a **private/incognito window** before you submit. If it asks you to log in or request access, it is not public.
>
> 📌 **NOTE:** The link goes in **this file only** (`MY_WORK.md`), **not** in `README.md`. Name your video file `StudentID_Assignment3_Demo.mp4`. It must last **2 to 3 minutes**.

---

## 🗺️ Work Roadmap (follow in this order)

| Step | What to do | Where | Marks |
|:----:|------------|-------|:-----:|
| 0 | Read `README.md`, read the full code, **run the original starter and save its output** (it fails on purpose) | Your IDE | – |
| 1 | Fork, rename, keep the repo **PUBLIC**, set your student ID (line 304), **commit** | GitHub + code | Part 1 (1) |
| 2 | Feature 1: Mutex lock on the ready queue, **commit** | Code | Part 2 (0.25) |
| 3 | Feature 2: Mutex lock(s) on the shared statistics, **commit** | Code | Part 2 (0.25) |
| 4 | Feature 3: Counting semaphore instead of busy waiting, **commit** | Code | Part 2 (0.5) |
| 5 | Development Log (5+ entries, different dates) | This file, Part A | Part 3 (0.5) |
| 6 | Reflection (4 questions) | This file, Part B | Part 3 (0.5) |
| 7 | Technical Answers (4 questions) | This file, Part C | Part 3 (0.5) |
| 8 | Record the video, upload it, paste the link above | Video + this file | Part 4 (1.5) |
| 9 | Final check, then submit the repo link on Blackboard | Blackboard | – |

> 💡 **TIP:** Tick each step off as you go. Do not leave the log, the reflection or the video for the last day.

---

## 🔁 Commit Rules (MANDATORY)

> ### ⚠️ MANY COMMITS ARE REQUIRED. A single bulk commit is penalized (-0.5 mark).

**Minimum: 4 meaningful commits. Aim for 7 or more.**

| # | Commit | Example message |
|:-:|--------|-----------------|
| 1 | Student ID set | `Set my student ID: 441234567` |
| 2 | Feature 1: Ready queue lock | `Feature 1: Protected the ready queue with a ReentrantLock` |
| 3 | Feature 2: Statistics locks | `Feature 2: Added locks to the shared statistics counters` |
| 4 | Feature 3: Semaphore | `Feature 3: Replaced busy waiting with a counting semaphore` |
| 5 | Development log entries | `Docs: Added development log entries 1-3` |
| 6 | Reflection and answers | `Docs: Completed reflection and technical answers` |
| 7 | Video link | `Docs: Added demo video link` |

**Rules:**
- ✅ **One commit per feature.** Do not put all three features in one commit.
- ✅ **Commit after each work session**, and after each part of this file.
- ✅ **Spread your commits over different dates.** Not all in one day.
- ❌ **Do not make all commits in the last hour** before the deadline (November 14, 2026).
- ❌ **No vague messages** like `done`, `update` or `final version`.

> 💡 **TIP:** Your commit history is checked and you **show it in your video** (at least 4 commits visible). Your development log dates should match your commit dates.
>
> 💡 **TIP:** **Use VS Code** (see *Recommended Development Environment* in `README.md` for the full setup). Sign in to GitHub in VS Code, then commit from the Source Control panel (Ctrl+Shift+G) → stage → write a message → Commit → Sync/Push. You can edit and commit this file the same way. **Pushing** matters: commits that are not pushed to GitHub are invisible to the instructor.

---

# Part A: Development Log (0.5 mark)

> ⚠️ **WARNING:** Minimum **5 entries**, spread over **different dates**. Five entries written on the same day, or written all at once at the end, will lose marks and look like a copy. Entry dates should be **between the start of the assignment and the deadline (November 14, 2026)**.
>
> 💡 **TIP:** Write an entry at the **end of each work session**, while you still remember what happened. It takes 5 minutes.
>
> 💡 **TIP:** Be specific. "Worked on the code" is a weak entry. "Added a `ReentrantLock queueLock` to `ReadyQueue` and wrapped the body of `poll()` in `lock()` / `try` / `finally { unlock() }`" is a strong one.
>
> 📌 **NOTE:** Each entry needs: date and time, what you did, details, challenges, solution, and time spent. Real challenges are fine (and expected). Do not invent fake ones.

## Example Entry (do not copy it, write your own)

### Entry 1 - [November 2, 2026, 4:30 PM]
**What I did**: Forked the repository, set my student ID, and ran the original starter

**Details**:
- Forked the starter repository and renamed it
- Changed student ID on line 304 to my actual ID (441234567)
- Ran the original program: 4 CPUs started, three of them picked `P1`, then `IllegalThreadStateException` and the watchdog stopped the program
- Saved the output in a text file for Question 1
- Committed and pushed: `Set my student ID: 441234567`

**Challenges**: I did not understand why the same process was picked by three CPUs

**Solution**: Read `ReadyQueue.poll()` again and found the `RaceWindow.pause()` between reading the head and removing it

**Time spent**: 45 minutes

---

## Your Development Log

### Entry 1 - [14 november .2026.5:30pm]
**What I did**:
Examine the original CPU scheduling simulation and read the assignment instructions.
**Details**:
Examine the assignment's README and PDF.MD.

To comprehend SharedStats, ReadyQueue, Process, and CpuWorker, I went over SchedulerSimulationSync.java.

Put 445050050 as my real student ID.

stored the results of running the initial starting code.

Several CPUs were found to have chosen P1, resulting in an IllegalThreadStateException.


**Challenges**:
At first, I couldn't figure out why different CPUs chose the same method.

**Solution**:
I found the race condition between reading the first queue member and discarding it by looking into ReadyQueue.poll().

**Time spent**:
1h
---

### Entry 2 - [Date and Time]
**What I did**:
To safeguard the shared ready queue, I implemented Feature 1.

**Details**:
ReentrantLock was imported.

queueLock was declared inside ReadyQueue.

Add(), poll(), processOf(), and snapshot() are protected.

Prior to accessing shared queue data, lock() was used.

To ensure that the lock is released, use try/finally.

**Challenges**:
Due to the presence of both a HashMap and a LinkedList in the ready queue, both data structures must maintain their consistency throughout concurrent access.


**Solution**:
To safeguard both structures and stop several CPUs from accessing or changing them at the same time, I utilized a single ReentrantLock.
**Time spent**:
1h
---

### Entry 3 - [Date and Time]
**What I did**:
Feature 2 was put into practice to safeguard shared statistics.

**Details**:
found that the shared variables were contextSwitchCount, completedProcessCount, and totalServiceTime.

Three distinct ReentrantLock objects were created.

three update methods were protected.

relevant getter methods.

kept inside the critical protected sections.

**Challenges**:
I had to choose between using a single lock for all statistics and a different lock for each variable.
**Solution**:
Since the three statistics are independent, I chose one lock for each variable. 
**Time spent**:
1h
---

### Entry 4 - [Date and Time]
**What I did**:
Feature 3's counting semaphore was put into practice.

**Details**:
Java.util.concurrent.Semaphore was imported.

set the ready queue semaphore's initial value to zero.

After adding a process to the ready queue, release() was added.

Acquire() was used to add awaitReady().

examined the relationship between available processes and semaphore permits.


**Challenges**:
At first, I didn't understand why the semaphore should begin at zero.

**Solution**:I discovered that the semaphore starts at zero and gets one permit each time a process is added because the ready queue is initially empty.

**Time spent**: 1h

---

### Entry 5 - [Date and Time]
**What I did**: CPU waiting was updated, and graceful shutdown was introduced.

**Details**:
used a blocking semaphore wait in place of the repeated polling method.

used thread and thread.start() to maintain the original process execution logic.join().

To awaken CPUs that were waiting on the semaphore, a shutdown signal was added.

After a CPU is granted a permit, a termination check is added.

verified that the CPU workers could stop working once every process was completed.

**Challenges**:
Preventing CPUs from staying blocked after the final process finished was the primary challenge.

**Solution**:
In order to awaken the waiting CPUs and enable them to verify the completion condition, I added a shutdown method that releases enough semaphore permits.

**Time spent**:
1h
---

### Entry 6 - [Optional - Date and Time]
**What I did**:The synchronization implementation was tested and examined.

**Details**:
compiled and ran the revised Java application.

examined the total service time, the number of context switches, and the number of completed processes.

verified that there were no busy-waiting polls.

examined the results of the verification.

compared the final implementation to the initial starter output.


**Challenges**:I had to make sure the synchronization solution didn't cause a deadlock or keep a CPU waiting indefinitely.

**Solution**:I ran the program several times, checking the verification block each time.

**Time spent**: 1h

---

## Development Log Summary

> 💡 **TIP:** Fill this in **last**, after all entries are written.

**Total time spent on assignment**: [X hours]

**Most challenging part**:

**Most interesting learning**:

**What I would do differently next time**:

---

# Part B: Reflection (0.5 mark)

> 🛑 **STOP:** Do **not** start this part until you have read the `README.md`, read the **entire** `SchedulerSimulationSync.java`, run it, and finished the three features.
>
> ⚠️ **WARNING:** Each answer must be **5 to 7 sentences**, in **your own words**. Copied or AI-generated answers without understanding get **0 marks for the whole assignment**. You may be asked to explain them in person.
>
> 💡 **TIP:** Mention concrete things you actually did: a method you wrote, an error you hit, a line of output you saw. Generic answers score low.
>
> 💡 **TIP:** Draft your answer in a few bullet points first, then turn them into sentences.

## Question 1: What did you learn about synchronization?

> 💡 **TIP:** Talk about race conditions (read-modify-write), critical sections, mutual exclusion with `ReentrantLock` and `try/finally`, the role of a counting semaphore, and what surprised you when the starter failed.

**Your Answer:** *(5-7 sentences)*

[I discovered that when several threads access shared resources simultaneously, synchronization is crucial. When two threads read and update the same variable without adequate protection, a race condition may occur. To ensure mutual exclusion and safeguard important portions of the ready queue and shared statistics, I employed ReentrantLock. Additionally, I discovered that try/finally guaranties that a lock is released even in the event that an exception interrupts an operation. By enabling CPUs to block until a process becomes available, the counting semaphore assisted in replacing busy waiting. The fact that the original program permitted multiple CPUs to choose the same process, resulting in an IllegalThreadStateException, shocked me the most.
]

## Question 2: What was the most challenging part of this assignment?

> 💡 **TIP:** Pick **one** specific challenge (understanding why the starter failed, choosing the lock granularity, the initial value of the semaphore, the shutdown of the CPUs, Git, the video) and say *why* it was hard.

**Your Answer:** *(5-7 sentences)*

[Implementing the semaphore shutdown mechanism was the most difficult aspect of this assignment. I initially grasped how acquire() blocks a CPU when the ready queue is empty, but I struggled to comprehend how the waiting CPUs ought to end. No new process will be added to the queue once the previous one is completed. As a result, CPUs that are awaiting the semaphore may be blocked indefinitely. In order to resolve this, I added a shutdown method that releases permissions to awaken the CPUs that were waiting. This section made it clearer to me that synchronization necessitates managing both regular program execution and program termination.]

## Question 3: How did you overcome the challenges you faced?

> 💡 **TIP:** Describe your method: reading the slides and the documentation, adding `System.out.println` to debug, running the program many times, re-reading the README, testing after each small change, asking for help.

**Your Answer:** *(5-7 sentences)*

By breaking the assignment up into three distinct features and working on each one gradually, I was able to overcome the difficulties. To find the race conditions, I first looked at the original code and the output. Next, I protected the shared statistics and the ready queue using ReentrantLock. I then put the semaphore into practice and used blocking synchronization in place of the busy-waiting mechanism. In order to find any potential mistakes, I also examined the README.md and tested the program after making modifications. In order to confirm that the shared values matched the expected values, I lastly reviewed the verification results.]

## Question 4: Where can synchronization concepts be applied in real-world applications?

> 💡 **TIP:** Use real applications you know (banking and money transfers, ticket or seat booking, a shared counter on a website, a print queue, a database) and connect each one to what you built here (shared data, critical section, lock or semaphore).

**Your Answer:** *(5-7 sentences)*

[In many real-world applications that enable multiple users or processes to access shared resources, synchronization is crucial. Locks in banking systems can stop two transactions from updating the same account balance in the wrong way. Synchronization stops two customers from booking the same seat at the same time when purchasing tickets online. Locks in databases preserve data consistency and safeguard shared records during updates. Access to a restricted set of resources, like printers or open connections, can also be managed with a semaphore. Because multiple threads need to coordinate their access to shared resources, these examples are comparable to my CPU scheduling project.]

### Optional: What would you like to learn more about?

[Any topics related to synchronization or operating systems that you're curious about?]

### Optional: How confident do you feel about synchronization concepts now?

[Beginner / Intermediate / Confident. What do you understand well? What needs more practice?]

### Optional: Feedback on the assignment

[Any comments? Was it helpful? Too easy or hard? Suggestions?]

---

# Part C: Technical Answers (0.5 mark)

> 🛑 **STOP:** You cannot answer these questions without understanding the code. Re-read `SchedulerSimulationSync.java` and **run it** first. Your answers must reference **your own code and your own output** (your student ID makes your output and your expected values unique).
>
> ⚠️ **WARNING:** Each answer must be **3 to 5 sentences**, with specific examples from your code or output. Use correct terms: race condition, critical section, mutual exclusion, mutex lock, semaphore, busy waiting, deadlock, producer, consumer.
>
> 💡 **TIP:** Keep the output of the **original starter** and the output of your **final version** in text files or screenshots, so you can copy real snippets for Question 1.

## Question 1: Race Condition in Your Own Output

**Question**: Run the **original starter** (before any fix) and paste the **verification block** of that run. Which value was wrong (expected vs observed)? Explain **step by step**, with two named threads/CPUs, how **one lost update** happens on one of the shared variables (read, `RaceWindow.pause()`, write). Why can the same bug happen on a real machine even without `RaceWindow`, and why is it hard to detect?

> ⚠️ **WARNING:** The snippet must come from **your own run** (with your student ID), not from a classmate or from this README.
>
> 💡 **TIP:** Use a small timeline: *CPU-1 reads `contextSwitchCount` = 12 → CPU-2 reads 12 → CPU-1 writes 13 → CPU-2 writes 13 → one increment is lost.* If your starter run crashed before printing numbers, run it several times (or paste the exception and the watchdog message and explain it).

**Your Answer:** *(3-5 sentences)*

[When several CPUs accessed the shared ready queue without mutual exclusion, the original starter created a race condition. CPU-1, CPU-4, CPU-2, and CPU-3 all chose P1 in my output, resulting in an IllegalThreadStateException. While busy-waiting polls reached 704, the verification revealed 17 context switches instead of 22, 8 finished processes instead of 10, and 41766 ms instead of 53100 ms. One increment could be lost, for instance, if CPU-1 and CPU-2 both read contextSwitchCount as 12, pause, and then write 13. Even without RaceWindow, thread execution can be interrupted between reading and writing, which can cause the same issue on actual machines.pause().]

Verification block of the **original starter**:
```
[Paste the verification block (or the exception/watchdog message) of the starter here]
```

Verification block of **my final version**:
```
[Paste the verification block of your final version here (all lines ✔)]
```

**Explanation of the timeline:**
[Explain the lost update step by step.]

## Question 2: Critical Sections and Lock Granularity

**Question**: List the **critical sections** you protected (variables and methods) and the lock(s) you used. **Lock granularity:** did you use **one lock** for the three statistics or **one lock per variable**? Why, and what is the trade-off? Why is the **ready queue** protected by a **different** lock than the statistics? Explain how your solution provides **mutual exclusion**, and discuss **progress** and **bounded waiting** (a default `ReentrantLock` is not fair: what does that imply?).

> 💡 **TIP:** The three counters are independent: does updating `contextSwitchCount` need to block an update of `totalServiceTime`? Also think about what could go wrong (deadlock, or long waiting) if the queue lock and the statistics lock were the **same** lock and a thread held it while doing something slow.

**Your Answer:** *(3-5 sentences)*

[I used a single ReentrantLock called queueLock to safeguard the ready queue operations, protecting both the HashMap and LinkedList. I protected contextSwitchCount, completedProcessCount, and totalServiceTime for the shared statistics using three different locks. Although it necessitates managing additional locks, this design enables independent statistics to be updated without needlessly blocking each other. Because the ready queue safeguards a different shared resource from the statistics, it employs a different lock. The default non-fair ReentrantLock does not ensure bounded waiting or prevent starvation, but these locks offer mutual exclusion and permit other threads to advance when a lock becomes available.]

| Critical section (variable / method) | Lock used | Why it needs protection |
|---|---|---|
| [e.g., `ReadyQueue.poll()`] | [lock name] | [reason] |
| [...] | [...] | [...] |

## Question 3: Busy Waiting vs Semaphore

**Question**: Describe the **busy waiting** of the starter and its cost (give the `Busy-waiting polls` number from your **starter** run). What does the **value of your semaphore** represent? What is its **initial value** and why? What is its value right after the `numProcesses` initial `add()` calls? Why does the last CPU call `release(totalCPUs)` at the end, and what would happen if it did not?

> 💡 **TIP:** Think about what a CPU does when the queue is empty in the starter, and what a CPU does in your final version (is it running, ready or blocked?). Also check what happens to a CPU blocked in `acquire()` when no process will ever be added again.

**Your Answer:** *(3-5 sentences)*

[Busy waiting and needless CPU activity resulted from the original starter's CPUs constantly checking the ready queue and sleeping for 20 milliseconds when it was empty. 704 busy-waiting polls were recorded in my initial output. Since the queue is initially empty, the counting semaphore, which in the final implementation represents the number of available processes in the ready queue, begins at zero. Assuming one release for each successful initial insertion and prior to any CPU obtaining a permit, its value increases to 10 after the first 10 processes are added. When all processes are completed, the final CPU releases totalCPUs permits to awaken waiting CPUs, as otherwise they might remain blocked indefinitely.]

## Question 4: Classical Problems and Deadlock

**Question**: The CPUs and the ready queue look like a classical synchronization problem of Chapter 5. **Name it**, and say who plays the **producer** and the **consumer** roles (careful: here the CPUs also re-enqueue processes). If the ready queue were **bounded** (capacity `K`), name the **three semaphores** you would need and their **initial values**. Describe a **deadlock scenario** that appears if a thread acquired the **mutex before** waiting on the semaphore (or if two locks were acquired in different orders), and say **which of the four necessary conditions** you would break to prevent it.

> 💡 **TIP:** Recall the bounded-buffer solution of the slides (`empty`, `full`, `mutex`) and the order of `wait()` calls in the producer and the consumer. For the deadlock, think about a producer that holds the mutex while waiting for a free slot that only a consumer (who needs the mutex) can create.

**Your Answer:** *(3-5 sentences)*
The ready queue is similar to the classical Producer-Consumer problem, also known as the bounded-buffer problem. The main thread acts as an initial producer, while CPUs act as consumers when removing processes and also as producers when re-enqueuing unfinished processes. For a bounded queue with capacity K, the three semaphores are empty initialized to K, full initialized to 0, and mutex initialized to 1. A deadlock could occur if a producer acquires the mutex and then waits for an empty slot while a consumer needs the same mutex to remove an item and release an empty slot. This can be prevented by breaking the hold-and-wait condition, for example by waiting for an available slot before acquiring the mutex.
**Classical problem and roles**:
[Name the problem; who is the producer, who is the consumer?]

**Semaphores for a bounded queue (name and initial value)**:
[Name the three semaphores and their initial values.]

**Deadlock scenario and prevention**:
[Describe the scenario and the necessary condition you would break.]

## Summary

**Key concepts I understood through these questions:**
1.
2.
3.

**Concepts I need to study more:**
1.
2.

---

# ✅ Final Checklist (complete before submitting)

> ⚠️ **WARNING:** Go through every line. Blackboard does not accept submissions after the deadline, which is **November 14, 2026**.

**Repository**
- [ ] Repository is **PUBLIC** (Settings → Danger Zone → Visibility)
- [ ] Repository is renamed to `OS-Assignment3-YourFirstName-YourLastName`
- [ ] GitHub account uses the university email (`@std.psau.edu.sa`)

**Code**
- [ ] Student ID is set in `SchedulerSimulationSync.java` (line 304)
- [ ] My code is based **only** on the starter of this repository (nothing copied from previous assignments)
- [ ] Code compiles and runs with no errors, and terminates by itself (no `⛔ WATCHDOG`)
- [ ] Feature 1 (ready queue lock), Feature 2 (statistics locks) and Feature 3 (semaphore, no busy waiting) all work
- [ ] **The four verification lines are ✔ in 5 consecutive runs**
- [ ] Every lock is released in a `finally` block
- [ ] `RaceWindow`, `Config`, the verification block and the watchdog are **unchanged**
- [ ] Each feature has clear comments

**Commits**
- [ ] **At least 4 meaningful commits, ideally 7 or more**
- [ ] **One commit per feature**
- [ ] Commits are spread over **different dates** (not all in the last hour)
- [ ] Everything is **pushed** to GitHub

**This file (`MY_WORK.md`)**
- [ ] Full name and student ID filled in at the top
- [ ] Development log has **5+ entries** on different dates
- [ ] Reflection: 4 questions, 5-7 sentences each
- [ ] Technical answers: 4 questions, 3-5 sentences each, with examples from **your** output (starter output **and** final output pasted in Question 1)
- [ ] No `[...]` placeholders left
- [ ] No section headers deleted

**Video**
- [ ] 2-3 minutes long, named `StudentID_Assignment3_Demo.mp4`
- [ ] Shows your name, ID, repository, 3 features (and your lock granularity choice), IDE execution with the verification block, one synchronization concept, and commit history
- [ ] Link is **public** (tested in an incognito window) and pasted in the **Video Link** section above

**Blackboard**
- [ ] Submit **only** the link to your public GitHub repository

> 🎯 **Good luck!** Start early, commit regularly, and make sure you can explain every line you submit.
