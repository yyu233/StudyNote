## Create Attribute and Method ##
Mock and MagicMock objects create all attributes and methods as you access them and store details of how they have been used. You can configure them, to specify return values or limit what attributes are available, and then make assertions about how they have been used.
Mock objects create attributes on demand. This allows them to pretend to be objects of any type. Mocks are callable and create attributes as new mocks when you access them. 

```
json = Mock()
json.dumps()
```
Notice two key characteristics of this mocked version of dumps():

Unlike the real dumps(), this mocked method requires no arguments. In fact, it will accept any arguments that you pass to it.

The return value of dumps() is also a Mock. The capability of Mock to recursively define other mocks allows for you to use mocks in complex situations


## Magic Mock ##
MagicMock is a subclass of Mock with all the magic methods pre-created and ready to use. There are also non-callable variants, useful when you are mocking out objects that aren’t callable: NonCallableMock and NonCallableMagicMock

## Patch ## 
The patch() decorators makes it easy to temporarily replace classes in a particular module with a Mock object. By default patch() will create a MagicMock for you. You can specify an alternative class of Mock using the new_callable argument to patch().

## Configure Mock ##
You can configure an existing Mock using .configure_mock()
