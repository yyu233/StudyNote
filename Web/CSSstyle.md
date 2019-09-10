You can apply inline styles directly to HTML elements with the style attribute. Alternatively, you can place CSS rules within style tags in an HTML document. Finally, you can write CSS rules in an external style sheet, then reference that file in the HTML document.  

An id is not reusable and should only be applied to one element. An id also has a higher specificity (importance) than a class so if both are applied to the same element and have conflicting styles, the styles of the id will be applied

## Selector ##

``` .class ``` class selector  
``` #id ``` id selector    
``` [attribute= value] ``` attribute selector

## Override style ##
It doesn't matter which order the classes are listed in the HTML element.   

However, the order of the class declarations in the <style> section are what is important. The second declaration will always take precedence over the first.
 
order << id atttribute << inline style << ```!important```   
 
