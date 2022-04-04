[Good Ref](https://www.cprogramming.com/tutorial/initialization-lists-c++.html)
```
class Demo
{
    Demo(int& val) 
     {
         m_val = val;
     }
private:
    const int& m_val;
};
By the C++ specification, this is illegal. We cannot change the value of a const variable in the constructor, because it is marked as const. So you can use the initialisation list:

class Demo
{
    Demo(int& val) : m_val(val)
     {
     }
private:
    const int& m_val;
};

```
