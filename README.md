# Priority Queueties

A playground for the implementation of different Priority Queues, as mentioned in the paper:  
A Survey on Priority Queue by Gerth Stølting Brodal.

# Motivation

I wanted a repository filled with different implementations of priority queues, so that I could reference them when building toy operating systems.

# Applications

There are many cases where one may want to use a priority queue. Since my interests are 
in operating systems, the bottom list applications of the data structure with a bias towards operating systems:

  * Process Scheduling. 
	  * A Scheduler may employ the use of a priority queue for determining which
    process to run. To do this, the scheduler assigns priorities to processes (usually with 
    IO bound processes higher than CPU bound processes).
    An example of this can be found in Minix, Xinu and Linux.

  * Semaphore Waiting Set. 
	  * With the use of semaphores, we may have multiple processes waiting on a signal. The scheduling of which process to run, when available, can be implemented with the use of a priority queue.
	  * Xinu (includes/semaphore.h) and Linux (include/semaphore.h, include/list.h) uses this implementation. Minix, which relies on message passing for interprocess communication and coordination, does not provide semaphore related system calls. 

  * Discrete Event Simulation - Event Scheduler. 
	  * Within a DES, there is an event ticker which keeps tracks of which events, and in which order, to execute. Events are often given a priority, and the priority queue can be seen as indicating when events are to be executed. NS3, a network DES, can be set to use ns3::PriorityQueueScheduler to manage events.
