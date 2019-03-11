## AutoWire ##

If using xml file, it saves you from writing any wiring code there. Using autowire attribute of a bean, we achieve the required functionality.

Please look at code below.

Config code without Auto-wiring:
```
<bean id="employee" class="com.Employee">   
    <property name="name" value="Dexter"></property>
</bean>

<bean id="employeeService" class="com.EmployeeService">
    <property name="employee" ref="employee"></property>
</bean>
```

Config code with Auto-wiring:
```
<bean id="employee" class="com.Employee">   
    <property name="name" value="Dexter"></property>
</bean>

<bean id="employeeService" class="com.EmployeeService" autowire="byName" /> 
```
Note that we did not have to write anything to refer property of EmployeeService i.e Employee. But still it was injected. Autowiring makes the container to search the bean configurations and do the collaboration among beans, with out the developer specifically mentioning these.
