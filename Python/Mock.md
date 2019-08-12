## Create Attribute and Method ##
Mock and MagicMock objects create all attributes and methods as you access them and store details of how they have been used. You can configure them, to specify return values or limit what attributes are available, and then make assertions about how they have been used.
Mock objects create attributes on demand. This allows them to pretend to be objects of any type. Mocks are callable and create attributes as new mocks when you access them. 

## Magic Mock ##
MagicMock is a subclass of Mock with all the magic methods pre-created and ready to use. There are also non-callable variants, useful when you are mocking out objects that aren’t callable: NonCallableMock and NonCallableMagicMock

## Patch ## 
The patch() decorators makes it easy to temporarily replace classes in a particular module with a Mock object. By default patch() will create a MagicMock for you. You can specify an alternative class of Mock using the new_callable argument to patch().
