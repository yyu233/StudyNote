Importing the module doesn't waste anything; the module is always fully imported (into the sys.modules mapping), so wether you use import sys or from sys import argv makes no odds.

The only difference between the two statements is what name is bound; import sys binds the name  sys to the module (so sys -> sys.modules['sys']), while from sys import argv binds a different name, argv, pointing straight at the attribute contained inside of the module (so argv -> sys.modules['sys'].argv). The rest of the sys module is still there, whether you use anything else from the module or not.

There is also no performance difference between the two approaches. Yes, sys.argv has to look up two things; it has to look up sys in your global namespace (finds the module), then look up the attribute argv. And yes, by using from sys import argv you can skip the attribute lookup, since you already have a direct reference to the attribute. But the import statement still has to do that work, it looks up the same attribute when importing, and you'll only ever need to use argv once. If you had to use argv thousands of times in a loop it could perhaps make a difference, but in this specific case it really does not.

The choice between one or the other then, should be based on coding style instead.
