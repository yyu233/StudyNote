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

```
@RestController
@RequestMapping("/home")
public class HomeContoller {
    @RequestMapping(value = "/groupId")
    String getGroupIdByValue(@RequestParam String groupId) {
        return "Group ID is "  + groupId;
    }
}
```

If request parameter is same as the controller method id, @RequestParam value can be omitted.   

```
@RestController
@RequestMapping("/home")
public class HomeController {
    @RequestMapping(value = {"/", "/view")
    String getHomeView() {
        return "This is home."
    }
}
```
Wildcard mapping. Request as "/home" or "/home/view" will all be mapped to getHomeView().    

```
@RestController
@RequestMapping("/home")
public class HomeController {
    @RequestMapping(value = "id")
    String getIdByValue(@RequestParam("id", default = "0") String userId) {
        return "User ID is " + userId;
    }
}
```
If the request parameter value is empty (i.e. "/home/id"), use the default value.    
