## WorkQueue ##

The main concept is that instead of executing the resouce-intensive task immediately, schedule the task to be done in the future.   
It is useful in the web application where handling a web request and getting a complicated task down consumes a lot of time.    

Runnning mulitiple worker process simultaneously to execute the task increases the scalability.   
