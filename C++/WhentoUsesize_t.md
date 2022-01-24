A good rule of thumb is for anything that you need to compare in the loop condition against something that is naturally a std::size_t itself.

std::size_t is the type of any sizeof expression and as is guaranteed to be able to express the maximum size of any object (including any array) in C++. By extension it is also guaranteed to be big enough for any array index so it is a natural type for a loop by index over an array.

If you are just counting up to a number then it may be more natural to use either the type of the variable that holds that number or an int or unsigned int (if large enough) as these should be a natural size for the machine.
