# cs3210---lab-1-solved
**TO GET THIS SOLUTION VISIT:** [CS3210 – Lab 1 Solved](https://www.ankitcodinghub.com/product/cs3210-lab-1-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;128038&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;4&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (4 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CS3210 - Lab 1 Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (4 votes)    </div>
    </div>
Processes, Threads and Synchronization Basics

Learning Outcomes

1. Understand the differences between processes and threads

2. Use the POSIX thread (pthread) library for shared-memory parallel programming

3. Implement critical sections in the code

4. Apply basic synchronization constructs in programs

5. Start to become familiar with our lab machines

You can obtain 2% of your grade in CS3210 by submitting your work at the end of the lab.

ò Why Learn fork(), pthreads, etc?

fork() / pthreads are relatively lower-level ways to create and synchronize processes and threads. However, it’s important to understand these intricacies before we explore the more abstracted and powerful libraries such as OpenMP / MPI.

. Programming Language: C vs C++

If you know C++, please do not use C++’s own std::thread, condvar/semaphore/mutex/unique lock, etc. in CS3210 unless specifically allowed. Please use pthreads.

ò Logging in &amp; Getting Started

For the lab and assignments, you are going to be running your code on the machines in the Parallel and Distributed Computing Lab located in COM1-B1-02. Use the following instructions to connect to the lab machines remotely over ssh.

Please follow https://nus-cs3210.github.io/student-guide/accessing/.

For this lab, connect to one of the machines using the guide above, and start working on completing the tasks in the lab. The lab files can be found here: https:

//www.comp.nus.edu.sg/~srirams/cs3210/L1_code.zip. You can use the command “wget” to download the code to the lab machine, and “unzip” to unzip the file.

1

Part 1: Processes vs. Threads

Multi-process programming on Linux with C++

Let us look at a simple program which demonstrates the use of processes in Linux. Open the ex1-processes.cpp file and study the use of the fork() system call and its return values.

Note the wait(nullptr) call by the parent process. The purpose of this call is to make sure the parent process waits until all its child processes are completed. In a situation where the child continues to run after the parent process is completed (died), the child is called an orphan process.

_• Compile the code in a terminal (console):

&gt; g++ -o processes ex1-processes.cpp

• Run the program in a terminal:

&gt; ./processes

x Exercise 1

Compile and run ex1-processes.cpp. Observe the output. Why is the line “We just cloned a process..!” printed twice? Fix the code such that the line only prints once.

Creating and terminating threads

1 for(size_t i = 0; i &lt; NUM_THREADS; i++)

2 {

3 printf(“main thread: creating thread %zu “, i);

4

5 //pthread_create spawns a new thread and return 0 on success

6 rc = pthread_create(&amp;threads[i], NULL, work, (void *)i);

7 }

Listing 1: Snippet of ex2-threads.cpp

ex2-threads.cpp contains a simple example on creating (spawning) threads with the pthread library and terminating them. In ex2-threads.cpp, the loop runs NUM THREADS number of times and calls the pthread create function to create/spawn new threads. pthread create takes in four arguments:

1. thread – Reference to a thread variable of type pthread t (element in threads array in this example) 2. attr – Thread attributes

3. start routine – The function to be executed by the newly spawned thread (function work in this example)

_• To find out more about different C++ functions, you can use the man (manual) command

in the terminal (console):

&gt; man pthread_create

• Compile the code in a terminal:

&gt; g++ -pthread -o threads ex2-threads.cpp

• Run the program in a terminal:

&gt; ./threads

x Exercise 2

Compile ex2-threads.cpp and run the program. Observe the output. Modify the NUM THREADS value and observe the order of thread execution. Do threads execute in the same order they are spawned each time the program runs? Is the final value of the variable counter always the same? Explain.

Part 2: Process and Thread Synchronization

A critical section is a section of code that uses mutual exclusion to ensure that:

• Only one thread at a time can execute in the critical section

• All other threads have to wait on entry

• When a thread leaves a critical section, another can enter

A race condition happens when two concurrent threads (or processes) access a shared resource without any synchronization. Race conditions arise in software when an application depends on the sequence or timing of processes or threads for it to operate correctly.

Process Synchronization with Semaphores

_ • Compile the code in a terminal:

&gt; g++ -pthread -o semaph semaph_named.cpp

• Run the program in a terminl:

&gt; ./semaph

Pitfalls: Named vs Unnamed Semaphores

Notice that we did not explicitly share our semaphore (sem) between parent and child processes. sem is shared correctly across all our processes because we used named semaphores through the POSIX sem open library call. This automatically causes sem to be in a shared memory region. If we used unnamed semaphores through the POSIX sem init library call, we would have to allocate the semaphore within shared memory ourselves. See man sem overview.

Read semaph shm.cpp to see the changes required for unnamed semaphores.

Thread Synchronization with Mutexes and Condition Variables

_• Compile the code in a terminal:

&gt; g++ -pthread -o race ex3456-race-condition.cpp

• Run the program in a terminal:

&gt; ./race

x Exercise 3

Compile ex3456-race-condition.cpp and run the program. Observe the output.

pthread join is a pthread library function which guarantees the caller thread that the target thread is terminated. In the program ex3456-race-condition.cpp, if the main thread calls pthread join for all the ADD and SUB threads before printing the final result of the global variable, we should see the real final value after all ADD and SUB threads are completed.

int pthread_join(pthread_t thread, void **retval);

Ð

pthread_join(thread, NULL); // example

x Exercise 4

Modify ex3456-race-condition.cpp (new name ex4-race-condition.cpp) to ensure that all ADD threads and SUB threads complete before printing the final result. Compile, run, and observe the output. (run multiple times to see if the output is consistent)

Mutexes

A mutex is a synchronization construct which is used to control access to a critical section in the code. A mutex variable acts like a lock and the thread that acquires the thread gets to access the critical section. Once a thread has acquired a mutex lock to a critical section, no other thread can acquire it until the first thread releases the mutex.

pthread mutex example pthread_mutex_t lock = PTHREAD_MUTEX_INITIALIZER;

pthread_mutex_lock(&amp;lock); // critical section here

pthread_mutex_unlock(&amp;lock);

x Exercise 5

Modify ex3456-race-condition.cpp (new name: ex5-race-condition.cpp) by adding a mutex variable to control access to the global counter. Compile, run, and observe the output. (Run multiple times to observe if the output is consistent!)

What do you think are the differences between a pthread mutex and a binary semaphore?

Condition variables

Mutexes provide a mechanism for controlling access to a critical section to prevent races. However, they cannot be used for threads to wait until another thread completes some arbitrary task. Condition variables provide a mechanism for threads to be signaled by other threads rather than continuously polling to check if a certain condition has been met. Condition variables are used in association with mutex variables. Related pthread functions are:

Ð• Create and destroy

pthread_cond_init(condition,attr), pthread_cond_destroy(condition)

• Waiting and signaling: pthread_cond_wait(condition,mutex), pthread_cond_signal(condition), pthread_cond_broadcast(condition)

Download and study ex6-cond-example.cpp which demonstrates the use of condition variables. The main thread creates three threads. Two of those threads increment a “count” variable, while the third thread watches the value of “count”. When “count” reaches a predefined limit, the waiting thread is signaled by one of the incrementing threads. The waiting thread “awakens” and then modifies count. The program continues until the incrementing threads reach TCOUNT. The main program prints the final value of count.

x Exercise 6

Modify ex3456-race-condition.cpp (new name: ex6-race-condition.cpp) using condition variables to prevent SUB threads from executing until all ADD threads are completed.

[ Further reading and examples: https://computing.llnl.gov/tutorials/pthreads/

Part 3: Producer-Consumer Problem (to be submitted)

In this part, we combine the first two parts to solve the producer-consumer problem using both (i) processes and semaphores, and, (ii) threads, mutexes and condition variables.

x Exercise 7

Implementing the same producer consumer logic with processes involves allocating memory from the kernel space as a means of maintaining a global variable (for inter-process communication). Refer to the example which uses shared memory with processes in semaph named.cpp.

x Exercise 8

Implement the exercise above but using processes and semaphores only (i.e.,, no pthreads, condition variables, etc). Name your program ex8-prod-con-processes.cpp.

The very basic approach of your program should be as follows:

// allocate shared memory // allocate semaphores

if (fork() == 0) producer(); // producer 1 if (fork() == 0) producer(); // producer 2 consumer();

// cleanup shared memory

x Exercise 9

Limit the total number of items produced/consumed to a sufficiently-large fixed value (to observe the performance of the programs accurately) and measure the time taken to complete the program for both cases (processes and pthreads). Then, vary this limit on the total number of items produced. Comment on the observations for your threads and processes implementations in exercises 7 and 8 (maximum length: 1 paragraph).

Pitfalls: Correctly exiting multi-threaded / multi-process programs

• The signal function (man 2 signal), and what code can run safely in a signal handler.

• The pthread sigmask function (man 3 pthread sigmask).

• How to indicate to running processes that they should exit.

• How to ensure processes do not deadlock when trying to exit.

-Lab sheet (2% of your final grade):

• Your code for the producer and consumer functions in ex7-prod-con-threads.cpp and ex8-prod-con-processes.cpp.

• Your answer for exercise 9.

Please use a legible monospace font (e.g. 11-point Consolas) with single line spacing for your code. Your answer for exercise 9 should also be in a legible font (no smaller than 11-point

Arial).

Appendix: Debugging

Viewing Processes and Threads

To view the running processes and threads in a Linux console, we can use ps and top/htop commands.

These commands should be invoked separately in a different terminal window.

To see a list of processes running on your system details, run any of the following commands in a terminal:

• &gt; ps -ef

• &gt; ps -A

• &gt; top

• &gt; htop

If too much information is printed and impossible to read at one time, you can pipe the output through the less command to scroll through them at your own pace:

&gt; ps -A | less

If you are looking for a specific process, e.g., bash, you can do

&gt; ps -A | grep bash

More information on ps: http://man7.org/linux/man-pages/man1/ps.1.html or type in man ps in the console.

To list individual threads under each process:

&gt; top -H

More information on top: http://man7.org/linux/man-pages/man1/top.1.html or type in man top in the console.

To kill a running process use either one of these commands:

• &gt; kill -p &lt;pid&gt;

• &gt; pkill

• &gt; killall

Debugging C / C++ Programs

There are multiple debugging tools available for debugging C programs. The gdb debugger is a command line debugger for C (and many other languages). To use the gdb debugger, we need to compile the source code with -g compiler flag. (When you compile with -g, the compiler includes debugging information in the binary, making it easier for gdb to find bugs.) gdb provides debugging features such as breakpoints, step execution, and, examining the call stack.

&gt;g++ -g -o prog prog.cpp

&gt; gdb prog

• Run the program inside gdb

&gt; run &lt;prog argument1&gt; &lt;prog argument 2&gt;

• Official gdb documentation https://ftp.gnu.org/old-gnu/Manuals/gdb/html_node/gdb_toc.html

Valgrind is a more advanced profiler which helps us debug applications as well as detect performance issues.

It includes advanced features such as detecting race conditions and false sharing.
