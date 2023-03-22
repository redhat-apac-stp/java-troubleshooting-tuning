# Java Troubleshooting & Tuning

## Fundamental

JVM Memory model
Relationship between Linux cgroup, JVM and pods

What is a cgropu?
What's the difference between cgroup v1 and v2?

Most Common Thread Related Issues

- `Race conditions` – two or more threads compete for changing a shared resource.
- `Deadlocks` – two or more threads stick, waiting after one another.
- `Livelocks` – two or more threads fail to meet the conditions to stop and continuously run without executing any useful work.
- `Starvation` – a thread is continuously blocked while the JVM executes other threads. The thread never gets to execute the instructions it defines.

Memory

- Stack
  - StackOverflowError
- Heap
  - OutOfMemoryError
- Metaspace  
  - OutOfMemoryError

## Profiling

- Tools
  - VisualVM
  - JProfiler (Commercial Product)
  - Java Mission Control (Oracle)
- Use it for
  - Identifying abnormal usage of resources
  - Finding out which part of code executes
  - Identifying slowness in app’s execution

### how to pass arguments to the java app

- VM
  - -Djava.rmi.server.hostname=localhost
- Container
  - Intro to Cryostat
- EAP
  - [TODO]

### how to find thread race condition

Symptoms

- GC cpu consumption is negligible
- Heap memory consumption dooesn't have peak and valley.
- Missing threads with expection in the logs
- exception message like `Exception in thread "Thread-1" java.lang.ArrayIndexOutOfBoundsException`
- app is not progressing; check the logs; logs are not getting generated.
- effective use of sync block can't be seen in the thread view.
- thread consuming 100% of the resource but not doing anything (no memory consumed).

- VM
  - VisualVM demo
- Container
  - [TODO]
- EAP
  - [TODO]

### how to identifying memory leaks

Symptoms

- GC doesn't have consistent peaks and valleys
- Consumed heap is always upwards
- logs have memory related error messages like `java.lang.OutOfMemoryError`
- app crashes

- VM
  - VisualVM demo
  - -Xmx1G & -Xms500m
- Container
  - [TODO]
- EAP
  - [TODO]

### how to find out which part of the code is executing (Sampling)



- VM
  - VisualVM demo
- Container
  - [TODO]
- EAP
  - [TODO]

### How to identify wrong behavior and optimization (instrumentation/profiling)


- VM
  - VisualVM demo
- Container
  - [TODO]
- EAP
  - [TODO]

### How to profile the app to identify SQL queries an app uses to communicate with a Database

- VM
  - VisualVM demo
- Container
  - [TODO]
- EAP
  - [TODO]

## EAP Troubleshooting & Best Practices
