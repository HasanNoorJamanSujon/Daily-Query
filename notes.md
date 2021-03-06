## REST
RESTful web application enables the client to take actions on server resources, 
such as create new resources (i.e. create a new user) or 
change existing resources (i.e. edit a post).
###  Idempotent
clients can make that same call repeatedly while producing the same result.
POST -> Not Idempotent, Otherwise all are Idempotent
Both PUT and POST can be used for creating. 
REST 6 constraints
https://medium.com/extend/what-is-rest-a-simple-explanation-for-beginners-part-2-rest-constraints-129a4b69a582
## IOC
IOC and DI develop loosely coupled applications which can be easily tested.
IOC- outsource of an object factory construction and management of objects.
create and manage objects
  


## DI 
Constructor injection (the good) -> for mandatory feild
Setter injection (the ugly) 	 -> for optional feild, Setter Injection Make Testing Easy
Field injection (the bad)	 -> head to use outside of spring container, Field Injection, a Unit Test Dies

@Configuration -> indicates that the class can be used by the Spring IoC container 
		  as a source of bean definitions.
@Bean -> annotation tells Spring that a method annotated with @Bean will return an object
	 that should be registered as a bean in the Spring application context

## GC

1. Prevent causing OutOfMemoryErrors.
2. Main objective of Garbage Collector is to free heap memory

We can also request JVM to run Garbage Collector. There are two ways to do it :
1. Using System.gc() method : System class contain static method gc() for requesting JVM to run Garbage Collector.
2. Using Runtime.getRuntime().gc() method : Runtime class allows the application to interface with the JVM in which the application is running. Hence by using its gc() method, we can request JVM to run Garbage Collector.

-Finalize method

It is a method that Garbage Collector always calls just before 
destroying the object which is eligible for Garbage Collection,
so as to perform clean-up activity. Clean-up activity means 
closing the resources associated with that object like Database
Connection, Network Connection or we can say resource de-allocation.
Remember it is not a reserved keyword.
Once finalize method completes immediately Garbage Collector
destroy that object. finalize method is present in Object class
The finalize() method called by Garbage Collector not JVM. 
Although Garbage Collector is one of the module of JVM.

## Thread

- Daemon thread

Daemon thread is a low priority thread that runs in background 
to perform tasks such as garbage collection.

Properties:

1. They can not prevent the JVM from exiting when all the user threads 
finish their execution.
2. JVM terminates itself when all user threads finish their execution
3. If JVM finds running daemon thread, it terminates the thread 
and after that shutdown itself. JVM does not care whether Daemon 
thread is running or not.
4. It is an utmost low priority thread.

- Polling
The process of testing a condition repeatedly till it becomes true is known as polling.
If it is true, certain action is taken. This waste many CPU cycles and makes the implementation inefficient.
To avoid polling, Java uses three methods, namely, wait(), notify() and notifyAll()
They must be used within a synchronized block only.

Thread methods how works internally 

1. wait() - It tells the calling thread to give up the lock and go to sleep until some other thread enters the same monitor and calls notify().

2. notify() - It wakes up one single thread that called wait() on the same object. It should be noted that calling notify() does not actually give up a lock on a resource.

3. notifyAll() - It wakes up all the threads that called wait() on the same object.

4. join() - thread1.join() => put thread1 running. only when thread1 finished 
its execution then next thread will start to execute.
5. yield() - Suppose there are three threads t1, t2, and t3. Thread t1 gets the processor and starts its execution and thread t2 and t3 are in Ready/Runnable state. Completion time for thread t1 is 5 hour and completion time for t2 is 5 minutes. Since t1 will complete its execution after 5 hours, t2 has to wait for 5 hours to just finish 5 minutes job. In such scenarios where one thread is taking too much time to complete its execution, we need a way to prevent execution of a thread in between if something important is pending. yeild() helps us in doing so.
yield() basically means that the thread is not doing anything particularly important and if any other threads or processes need to be run, they should run. Otherwise, the current thread will continue to run.

6. sleep() - This method causes the currently executing thread to sleep for the specified number of milliseconds, subject to the precision and accuracy of system timers and schedulers. The argument value for milliseconds can’t be negative, else it throws IllegalArgumentException.
Thread.sleep() is used to pause the main thread execution for 2 seconds.
Any other thread can interrupt the current thread in sleep, in that case InterruptedException is thrown.

- hashcode and equals
1. hashCode() : For every object, JVM generates a unique number which is hashcode. It returns distinct integers for distinct objects. A common misconception about this method is that hashCode() method returns the address of object, which is not correct. It convert the internal address of object to an integer by using an algorithm. The hashCode() method is native because in Java it is impossible to find address of an object, so it uses native languages like C/C++ to find address of the object.

Use of hashCode() method : Returns a hash value that is used to search object in a collection. JVM(Java Virtual Machine) uses hashcode method while saving objects into hashing related data structures like HashSet, HashMap, Hashtable etc. The main advantage of saving objects based on hash code is that searching becomes easy.
Note : Override of hashCode() method needs to be done such that for every object we generate a unique number. For example,for a Student class we can return roll no. of student from hashCode() method as it is unique.

*** objects which are .equals() MUST have the same .hashCode().

- Object class 
Every class in Java is directly or indirectly derived from the Object class
Hence Object class acts as a root of inheritance hierarchy in any Java Program.
Methods 
toString()
hashcode()
equals()
getClass() 
finalize()
clone()
wait()
notify()
notifyAll()

Callable interface in concurrency package that is similar to Runnable interface but it can return any Object and able to throw Exception. 

- this and super

1. We can use super() as well this() only once inside constructor. If we use super() twice or this() twice or super() followed by this() or this() followed by super(), then immediately we get compile time error i.e, we can use either super() or this() as first statement inside constructor and not both.

2. It is upto you that whether you use super() or this() or not because if we are not using this() or super() then by default compiler will put super() as first statement inside constructor. 

### Interface and Abstract class
Interface 
1. support multiple inheritance
2. set of common behaviors
3. the class implements and agree with its behaviors
4. add lot of flexibility in system
*** what the object can do

Abstract class
1. can't create object, only extends
2. type of templete for subclasses 
3. no implimentation just declaration
*** what the object is

### Static class
1. only nested class can be static
2. nested static class dosen't need outer class reference
3. static class can't access non static member of outer class

### final vs const
final - grab memory when to access > good
const - grap memory when compile > less good

instance variable can be final but not const

### Dart
1. All data types are object
2. functions are also object
3. Dynamic and staticly typed 
4. optional parameter

### Blockchain
Distributed ledger technology
1. transaction can't be changed of modify

peer to peer monetary system
no middle man needed
imposible to hide anything


