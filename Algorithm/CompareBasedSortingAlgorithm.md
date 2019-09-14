Proposition: Any compare based sorting algorithm needs at least ``` log(N!) ~ Nlog(N) ``` compares at the worst case. 

Proof:
1. Assume array contains N distinct values from a1 to an.
2. Worst case is dictated by the height h of decision tree.
3. Binary tree of height h has at most ``` 2^h ``` leaves.
4. N! orderings: at least N! leaves. 

Lower bound may not hold if the algorithm has: 
* The initial order of the input
* The ditribution of key values
* The representation of keys
