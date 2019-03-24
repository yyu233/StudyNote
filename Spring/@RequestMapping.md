When configuring Spring MVC, we need to specify the mapping between request and handler method. 

```
@RestController
@RequestMapping("/file")
public class FileController {
    @RequestMapping("/index") 
    String index() {
        return "Index file"; 
    }
}
```

request "/file/index" will be handled by index(). 

```
@RestController
@RequestMapping("/home")
public class HomeController {
    @RequestMapping(value = "/id")
    String getIdByValue(@RequestParam("id") String userId) {
        return "User ID is " + userId; 
    }
}
```
request /home/id?id=1 will be handled by getIdByValue. id will match to userId.   
