···

class BrokenComparison:   
    def __eq__(self, other):   
        return True   
b = BrokenComparison()    
b == None  # Equality operator    
True    
b is None  # Identity operator    
False   
···
