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

## Disadvantages of Denormalization ## 

* Disk space:    
This is expected, as we’ll have duplicate data.
*  Data anomalies:   
We have to be very aware of the fact that data now can be changed in more than one place. We must adjust every piece of duplicate data accordingly. That also applies to computed values and reports. We can achieve this by using triggers, transactions and/or procedures for all operations that must be completed together.
Documentation: We must properly document every denormalization rule that we have applied. If we modify database design later, we’ll have to look at all our exceptions and take them into consideration once again. Maybe we don’t need them anymore because we’ve solved the issue. Or maybe we need to add to existing denormalization rules. (For example: We added a new attribute to the client table and we want to store its history value together with everything we already store. We’ll have to change existing denormalization rules to achieve that).
* Slowing other operations:    
We can expect that we’ll slow down data insert, modification, and deletion operations. If these operations happen relatively rarely, this could be a benefit. Basically, we would divide one slow select into a larger number of slower insert/update/delete queries. While a very complex select query technically could noticeably slow down the entire system, slowing down multiple “smaller” operations should not damage the usability of our application.
* More coding:  
Rules 2 and 3 will require additional coding, but at the same time they will simplify some select queries a lot. If we’re denormalizing an existing database we’ll have to modify these select queries to get the benefits of our work. We’ll also have to update values in newly-added attributes for existing records. This too will require a bit more coding.

[Reference](https://www.vertabelo.com/blog/technical-articles/denormalization-when-why-and-how)
