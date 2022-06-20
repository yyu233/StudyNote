Junit uses Reflection especially for testing Private/Protected methods.
For Private methods,
```
Method method = targetClass.getDeclaredMethod(methodName, argClasses);
method.setAccessible(true);
return method.invoke(targetObject, argObjects);
```
For private fields,
```
Field field = targetClass.getDeclaredField(fieldName);
field.setAccessible(true);
field.set(object, value);
```
