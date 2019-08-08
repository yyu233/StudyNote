Python object.c: 
```
/* Test whether an object can be called */

int
PyCallable_Check(PyObject *x)
{
    if (x == NULL)
        return 0;
    if (PyInstance_Check(x)) {
        PyObject *call = PyObject_GetAttrString(x, "__call__");
        if (call == NULL) {
            PyErr_Clear();
            return 0;
        }
        /* Could test recursively but don't, for fear of endless
           recursion if some joker sets self.__call__ = self */
        Py_DECREF(call);
        return 1;
    }
    else {
        return x->ob_type->tp_call != NULL;
    }
}

```

1. If an object is an instance of some class then it is callable iff it has __call__ attribute.
2. Else the object x is callable iff x->ob_type->tp_call != NULL
```
Desciption of tp_call field:
ternaryfunc tp_call An optional pointer to a function that implements calling the object. This should be NULL if the object is not callable. The signature is the same as for PyObject_Call(). This field is inherited by subtypes.
```
