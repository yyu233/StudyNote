WeakReference has a shorter lifecycle than SoftReference.

```
String str = new String("abc");

WeakReference<String> abcWeakRef = new WeakReference<>(str);
str = null;
```

