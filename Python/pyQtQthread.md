Qt, and therefore PyQt, provides its own infrastructure to create multithreaded applications using QThread. PyQt applications can have two different kinds of threads:

Main thread
Worker threads
The application’s main thread always exists. This is where the application and its GUI run. On the other hand, the existence of worker threads depends on the application’s processing needs. For example, if your application commonly runs heavy tasks that take a lot of time to finish, then you might want to have worker threads to run those tasks and avoid freezing the application’s GUI.
