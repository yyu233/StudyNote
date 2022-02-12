There is one functional reason for using a different tag between the typedef and the struct. This is when you're doing a linked list structure, where one of the fields in your struct is a pointer to an instance of the struct being defined. Since the statement isn't complete yet, you can't use the typedef name within the statement.

For example:
```
typedef struct {
    link_t *next;
    void   *data;
} link_t;
won't work, because you're trying to use link_t before the compiler has seen the symbol. Instead, you write it so:

typedef struct LL {
    struct LL *next;
    void      *data;
} link_t;
```
and struct LL is known to the compiler one line before you use it.
