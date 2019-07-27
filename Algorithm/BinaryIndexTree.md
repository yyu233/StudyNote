Thoughts are triggered by leetcode 307.    

My initial approach is to use 2d array to memorize the last range sum from i to j. But it cannot solve the problem, for instance, when update is called, I cannot think of from which range and how many range sum I need to update from a global scope of 2d array. My approach is limited only to the case when range sum is called just next to last update call. 

I read this post which is very helpful for understanding how Binary Index Tree works and how BIT can efficiently solve this problem. 
[Here is the link](https://www.hackerearth.com/practice/data-structures/advanced-data-structures/fenwick-binary-indexed-trees/tutorial/)    
[Second link](https://www.topcoder.com/community/competitive-programming/tutorials/binary-indexed-trees/)


I am trying to simulate and trace back how this algorithm is invented at a high level idea. The first step is always to think about how to formulate a valid quesiton. For this problem, we want to find a way to make the update know how many range sum needs to update. Is there any way that we can maximize the utilization of array space? Since we are dealing with integers, is there any property of integer can help us to do some masking job without adding extra spaces? We can represent integer in binary and some property may help us. To be specific, when we update a single value at an arbitary index, we should somehow decipher some encrpted information from the index to know how many range sum and the range to update. 

Valid quesiton (correct direction) -> potential solution -> validate 
