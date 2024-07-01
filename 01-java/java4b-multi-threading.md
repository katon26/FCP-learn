## Multi-Threading in Java
- Multithreading is a powerful feature in Java that allows concurrent execution of two or more parts of a program for maximum utilization of CPU, called threads, to efficiently utilize system resources and can improve the performance of the application
- Java provides built-in support for multithreaded programming, allowing multiple threads to run concurrently
- Multithreading enables application to perform multiple tasks simultaneously, such as listening for user input while performing background tasks

- [Lifecycle of a Thread](#lifecycle-of-a-thread)
- [Thread Syncronization](#thread-synchronization)
- [Inter-thread Communication](#inter-thread-communication)

### Lifecycle of a Thread
- New: The thread is in this state before an instance of the thread is created. The thread is considered not alive.
- Runnable: The thread is in this state after the instance of the thread is created and before the start() method is called. The thread is considered alive.
- Running: The thread is in this state after the start() method is called and before the run() method is completed. The thread is considered alive.
- Non-Runnable (Blocked): The thread is in this state when it is still alive but is blocked and waiting for a resource.
- Terminated: The thread is in this state when the run() method is completed or the stop() method is called. The thread is considered not alive.

ChatGPT Prompt:
```
1. Could you describe in more detail each stage in the life cycle of a thread in Java?
2. Provide a more detailed example of how these stages might apply to a thread processing a transaction in a banking application in Java Programming Language.
```

### Thread Synchronization
- Synchronization in Java is the capability to control the access of multiple threads to any shared resource
- Without synchronization, one thread can modify a shared resource while another thread is in the process of using or updating the same resource, leading to data inconsistency
- This can lead to significant issues in multithreaded applications
- Syncronization can be achieved using the synchronized keyword, locks, and other mechanisms like wait(), notify(), and notifyAll() methods

ChatGPT Prompt:
```
1. Can you explain in more detail how synchronization works in Java multithreading?
2. Provide a more detailed example of how synchronization could be used to manage access to a shared customer account data in a banking application in Java Programming Language.
```

### Inter-thread Communication
- Inter-thread communication is a mechanism in which a thread is paused running in its critical section and another thread is allowed to enter (or lock) in the same critical section to be executed
- Inter-thread communication allows synchronization of threads to communicate with each other
- Methods like `wait()`, `notify()`, and `notifyAll()` are used for inter-thread communication in Java
- These methods are used in synchronization context - within synchronized methods or blocks

ChatGPT Prompt:
```
1. Can you explain in more detail how methods like wait(), notify(), and notifyAll() work for inter-thread communication in Java?
2. Provide a more detailed example of how one thread might notify another in a banking application in Java Programming Language.
```
