## Module Private vs Class Private ## 

**Module private** starts with one underscore
Such a element is not copied along when using the from <module_name> import * form of the import command; it is however imported if using the import <moudule_name> syntax 

**Class private** starts with two underscores (aka dunder i.e. d-ouble under-score) 
Such a variable has its name "mangled" to include the classname etc.
It can still be accessed outside of the class logic, through the mangled name.
