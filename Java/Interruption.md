Ex 1:
Use flag. It is not good beacause when thread sleeps, it is in the blocked state. There will be a latency for the thread to be 
aware of state change of flag. 

```
public classs NewThread extends Thread {
    
    private volatile boolean canceled;
    public NewThread(String name) {
        super(name);
        canceled = false;
    }
    
    public void setCancel() {
        canceled = true;
    }
    @Override
    public void run() {
        while (canceled) {
            try {
                Thread.sleep(5000);
            } catch (InterruptedException e) {
                System.out.println(Thread.currentThread().getName() + " is interrupted);
                System.out.println("Interrupted flag is " + Thread.isInterrupted());
            }
        }
    }
}
```
