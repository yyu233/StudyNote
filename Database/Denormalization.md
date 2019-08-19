## Denormalization ## 

Denormalization is a strategy used on a previously-normalized database to increase performance. The idea behind it is to add redundant data where we think it will help us the most. We can use extra attributes in an existing table, add new tables, or even create instances of existing tables. The usual goal is to decrease the running time of select queries by making data more accessible to the queries or by generating summarized reports in separate tables.    

## When to Use Denormalization ##

* Maintaining history:   
Data can change during time, and we need to store values that were valid when a record was created. What kind of changes do we mean? Well, a person’s first and last name can change; a client also can change their business name or any other data. Task details should contain values that were actual at the moment a task was generated. We wouldn’t be able to recreate past data correctly if this didn’t happen. We could solve this problem by adding a table containing the history of these changes. In that case, a select query returning the task and a valid client name would become more complicated. Maybe an extra table isn’t the best solution.
* Improving query performance:    
Some of the queries may use multiple tables to access data that we frequently need. Think of a situation where we’d need to join 10 tables to return the client’s name and the products that were sold to them. Some tables along the path could also contain large amounts of data. In that case, maybe it would be wise to add a client_id attribute directly to the products_sold table.
* Speeding up reporting:   
We need certain statistics very frequently. Creating them from live data is quite time-consuming and can affect overall system performance. Let’s say that we want to track client sales over certain years for some or all clients. Generating such reports out of live data would “dig” almost throughout the whole database and slow it down a lot. And what happens if we use that statistic often?
Computing commonly-needed values up front: We want to have some values ready-computed so we don’t have to generate them in real time.
