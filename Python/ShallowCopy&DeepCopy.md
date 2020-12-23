

    A shallow copy constructs a new compound object and then (to the extent possible) inserts references into it to the objects found in the original.

    A deep copy constructs a new compound object and then, recursively, inserts copies into it of the objects found in the original.

Two problems often exist with deep copy operations that don’t exist with shallow copy operations:

    Recursive objects (compound objects that, directly or indirectly, contain a reference to themselves) may cause a recursive loop.

    Because deep copy copies everything it may copy too much, such as data which is intended to be shared between copies.



