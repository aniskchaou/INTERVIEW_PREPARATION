## **What is a `Thread`?**

Ans: In Java, the flow of a execution is called Thread. Every java program has at least one thread called main thread, the Main thread is created by JVM.

## **How do you make a `thread` in Java?**

**Extend Thread class:**

**Extending a Thread class and override the run method**. The thread is available in java.lang.thread.

```
Public class  Addition extends  Thread {

public  void  run () {
}

}

```

**The disadvantage of using a thread class is that we cannot extend any other classes because we have already extend the thread class**.

**Implement Runnable interface:**

```
Public class  Addition implements  Runnable {

public  void  run () {

}
}

```

## **Explain about join () method.**

Join () method is used to join one thread with the end of the currently running thread.

```
public  static  void  main (String[] args){

Thread t = new  Thread ();
t.start ();
t.join ();

}
}

```

## **Difference between `notify()` method and `notifyAll()` method in Java.**

**`notify()`**  This method is used to send a signal to wake up a single thread in the waiting pool.  **`notifyAll()`**  This method sends the signal to wake up all the threads in a waiting spool.

## **When to use Runnable interface Vs Thread class in Java?**

Ans: If we need our class to extend some other classes other than the thread then we can go with the runnable interface because in java we can extend only one class.

If we are not going to extend any class then we can extend the thread class.

## **Difference between start() and run() method of thread class.**

Start() method creates new thread and the code inside the run () method is executed in the new thread.

## **What is `Multi-threading`?**

Multiple threads are executed simultaneously.

```
public  class  MultipleThreads implements  Runnable
{

public  static  void  main (String[] args){

Runnable r = new  runnable ();
Thread t=new  thread ();
t.start ();//User thread  starts  here
Addition add=new  addition ();
}

public  void  run(){
go();
}
}

```

## **Explain thread life cycle in Java.**

-   New
-   Runnable
-   Running
-   Non-runnable (Blocked)
-   Terminated

## **What is Synchronization?**

Ans: Synchronization makes only  **`one thread to access a block of code at a time.`**

```
public  class  ExampleThread  implements  Runnable{ 

public  static  void  main (String[] args){
 Thread t = new Thread ();
  t.start ();
   } 
  
  public  void  run(){ 
  synchronized(object){ {
  
   }
   }

```
