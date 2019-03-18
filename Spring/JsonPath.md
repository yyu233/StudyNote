[JsonPath](https://github.com/json-path/JsonPath)

E.g.
```
$.shelf[0].book[1].title
$['shelf'][0]['book'][1]['title']
$.shelf[0].book[?(@.price < 10)].title

```
