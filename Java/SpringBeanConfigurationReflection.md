Spring uses bean configuration such as:

```
<bean id="someID" class="com.example.Foo">
    <property name="someField" value="someValue" />
</bean>
````
When the Spring context processes this < bean > element, it will use Class.forName(String) with the argument "com.example.Foo" to instantiate that Class.

It will then again use reflection to get the appropriate setter for the < property > element and set its value to the specified value.
