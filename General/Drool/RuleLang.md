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
