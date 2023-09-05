# Student-Teaching-Assistant
Multi-threaded C program that simulates a scenario where students are waiting to be taught by a Teaching Assistant (TA) in an office. 

The provided code is a multi-threaded C program that simulates a scenario where students are waiting to be taught by a Teaching Assistant (TA) in an office. The program uses POSIX threads (pthread) for thread management and semaphores for synchronization between students and the TA. Here's a brief introduction to the code:

Initialization: The program starts by including necessary C libraries, defining constants like the number of seats (NUM_SEAT) and maximum sleep time (SLEEP_MAX), and initializing variables and data structures.

Thread Creation: It creates two types of threads - the TA thread and student threads. The TA thread (ta) represents the TA, while the student threads (students) represent individual students. Each student is given a unique ID, and their status is tracked using the studentStatus array.

Synchronization: Semaphores (sem_stu and sem_ta) are used for synchronization between students and the TA. These semaphores control the flow of students waiting and the TA's availability for teaching.

Teaching Process: Students arrive, try to take a seat in the waiting area (limited by NUM_SEAT), and wait for their turn to be taught by the TA. The TA teaches one student at a time, and once a student is taught, they exit the program. Students can also leave if they cannot find a seat.

Thread Joining: After creating the threads, the program waits for the TA thread and all student threads to finish their execution using pthread_join. This ensures that the program doesn't terminate prematurely.

Student States: Students can be in three different states: 0 (waiting), 1 (learning), and 2 (finished learning), which are tracked using the studentStatus array. These states represent whether a student is waiting for their turn, actively learning from the TA, or has finished their learning session and is ready to leave.
