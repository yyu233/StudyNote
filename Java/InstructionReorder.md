cpu A update variable and writes to the buffer. The variable in the buffer holds the newest value. cpu A reads from main memory. The variable holds the old value.
This instruction excution order results in an unwanted value if we don't force cpu to flush buffer and read. 

[Some Reference](https://www.jianshu.com/p/b4d4506d3585) 
