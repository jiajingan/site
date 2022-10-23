---
title: "Operating Systems"
date: 2022-10-23T12:23:22-04:00
draft: true
---

In this post I will relearn about Operating Systems and concurrency.
---

- What is concurrency?
    - Concurrency is the ability to run several programs or processes in parallel. It will improve throughput and interactivity of the program. Being able to leverage all multiple cores properly will achieve success in concurrency.
- Resources
    - https://www.vogella.com/tutorials/JavaConcurrency/article.html
    - https://www.baeldung.com/java-common-concurrency-pitfalls
    - https://thecodest.co/blog/asynchronous-and-single-threaded-javascript-meet-the-event-loop
    
- What is a Process vs Thread
    - A process runs independently and it can not directly access another process data. The resource of the process is allocated from the OS such as memory and CPU.
    - A thread is like a light weight process and it has it's own stack that can access shared data with other threads at the same time in the same process. Every thread has it's own memory cache and it reads and stores in it's own cache. A thread can reread shared data. 
- What is the difference between asynchronous vs synchronous code
    - Synchronous code is single-thread code that runs one operation at a time. 
    - Asynchronous code is multi-thread code that can run operations in parallel
- Concurrency Problems and Issues
    - The runtime can be limited as the task and subtasks increases
    - Threads has a call stack such as access share data that has two problems, visibility and acess problems.
        - Visibility problem is when thread A reads shared data which is changed by thread B without thread A knowing. 
        - Access problem is when several threads access and change the same shared data at the same time.
    - These problems can lead to
        - Liverness failure, when the program doesn't react anymore due to concurrent access of data e.g. deadlocks(when processes are held by another process and another....).
        - Safety failure, the program creates incorrect data.