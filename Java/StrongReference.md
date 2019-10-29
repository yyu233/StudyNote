```
Object strong = new Object();

```

ArrayList Source Code:

```
private transient Object[] elementData;

public void clear() {
    modCount++;
    
    //only to weaken the reference of element of array but keep the strong reference of array in case add() is invoked in the future to       //avoid memory allocation again. 
    for (int i = 0; i < size; i++) {
        elementData[i] = null;
    }
    size = 0;
}

```
