Firstly, "hashing" (using a cryptographic one way function) is not "encrypting". In encryption, you can reverse the process (decryption). In hashing, there is (theoretically) no feasible way of reversing the process.

A hash is some function f such that v cannot be determined from f(v) easily.

The point of using hashing for authentication is that you (or someone seeing the hash value) do not have any feasible way (again, theoretically) of knowing the password. However, you can still verify that the user knows his password. (Basically, the user proves that he knows v such that f(v) is the stored hash).

The weakness of simply hashing (aside from weak hash functions) is that people can compile tables of passwords and their corresponding hash and use them to (effectively) get the inverse of the hash function. Salting prevents this because then a part of the input value to the hash is controlled and so tables have to be compiled for that particular salt.
