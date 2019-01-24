## Rule Language ##
Rough Format: 

```
rule "name"
    attributes
    when
        LHS
    then
        RHS
end
```

Pattern Binding: 

```
rule "pattern binding" 
   when
        $p: Person()
   then 
        System.out.println(Person + $p);
        
end
```

Pattern:

```
    pattern binding : pattern typer ( constraints )
    
```
The type need not be the actual class of some fact objects. It can be super class or interfaces.
