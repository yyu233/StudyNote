``` wait() ```   
1. wait() method releases the lock.
2. wait() is the method of Object class.
3. wait() is the non-static method - public final void wait() throws InterruptedException { //...}
4. wait() should be notified by notify() or notifyAll() methods.
5. wait() method needs to be called from a loop in order to deal with false alarm.
6. wait() method must be called from synchronized context (i.e. synchronized method or block), otherwise it will throw IllegalMonitorStateException

``` sleep() ```   
1. sleep() method doesn't release the lock.
2. sleep() is the method of java.lang.Thread class.
3. sleep() is the static method - public static void sleep(long millis, int nanos) throws InterruptedException { //... }
after the specified amount of time, sleep() is completed.
4. sleep() better not to call from loop(i.e. see code below).
5. sleep() may be called from anywhere. there is no specific requirement.



