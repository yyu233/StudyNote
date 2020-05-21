```
for(int i = 0, n = s.length() ; i < n ; i++) { 
    char c = s.charAt(i); 
}
for(char c : s.toCharArray()) {
    // process c
}
```
for placing the s.length() in the initialization expression. If anyone doesn't know why, it's because that is only evaluated once where if it was placed in the termination statement as i < s.length(), then s.length() would be called each time it looped
