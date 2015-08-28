# Threads-and-Non-blocking-Reusable-Controls

___
#####When and why we will use Threads in our programs?
  One usecase is when you have a long running operation and you still wanna keep the main thread free for UI/input.
  
  Another usecase is when you wanna take advantages of modern CPU's, which have multiple cores. Without using threads its only    possible to use one core  
  
___
#####Explain about the Race Condition Problem and ways to solve it in Java
  A Race Condition Problem is when two or more threads access a varible almost simultaneously, resulting in unexpected behavior   such as a varible being incremented by 1 instead of 2
  
  To solve these kind of problems Java has build in syncronization features. These features work by for example, only allowing one thread inside a method at a time.    

___
#####Explain how Threads can help us in making responsive User Interfaces
   If you have a long running operation it will freeze the UI, Since all UI related stuff is running on the main thread.
   Therefore if you wanna use the UI while doing long operations, you'll have to move that operation to another thread 
   
___
#####Explain how we can write reusable non-blocking Java Controls using Threads and the observer Pattern
  By implementing Runnable/Callable on RandomUserControl, its possible to start a new Thread like so
  
```Java
    new Thread(RandomUserControl).start()
```
  If we also implement Observable on RandomUserControl, we can then subscribe to updates from a class that implements Observer
  like so. this also includes the benefit of Observer not needing to know about the Observable
  
  ```Java
    randomUserControl.addObserver(this);
```
  
