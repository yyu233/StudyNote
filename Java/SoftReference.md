```
Browser prev = new Browser();

SoftReference sr = new SoftReference(prev);

if (sr.get() != null) {
    rev = (Browser) sr.get();
} else {
    prev = new Browser();
    sr = new SoftReference(prev);
}

```
