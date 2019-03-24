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

```
@RestController
@RequestMapping("/home")
public class HomeController {
    @RequestMapping(method = RequestMethod.GET)
    String get() {
        return "Http GET";
    }
    @ReqeustMapping(method = RequestMethod.POST)
    String post() {
        return "Http POST";
    }
    @RequestMapping(method = RequestMethod.DELETE)
    String delete() {
        return "Http DELETE";
    }
    @RequestMapping(method = RequestMethod.PUT)
    String put() {
        return "Http PUT";
    }
    @RequestMapping(method = RequestMethod.PATCH)
    String patch() {
        return "Http PATCH";
    }
}
```
By default, all request are assumed to match to Http Get, but we can specify the request type in @RequestMapping.   

```
@RestController
@RequestMapping("/home")
public class IndexController {
  @RequestMapping(value = "/prod", produces = {"application/JSON"})
  @ResponseBody
  String getProduces(){
    return "Produces attribute";
  }
  
  @RequestMapping(value = "/cons", consumes = {"application/JSON", "application/XML"})
  String getConsumes(){
    return "Consumes attribute";
  }
}
```
In this code, the getProduces() handler method produces a JSON response. The getConsumes() handler method consumes JSON as well as XML present in requests.

```
@RestController
@RequestMapping("/home")
public class HomeController {
  @RequestMapping(value = "/head", headers = {"content-type=text/plain"})
  String post(){ 
    return "Mapping applied along with headers"; 
  } 
}
```
Map the request based on value and the header content.    

```
@RestController
@RequestMapping("/home")
public class IndexController {
  @RequestMapping(value = "/fetch/{id}", method = RequestMethod.GET)
  String getDynamicUriValue(@PathVariable String id){
    System.out.println("ID is "+id);
    return "Dynamic URI parameter fetched";						
  } 
  @RequestMapping(value = "/fetch/{id:[a-z]+}/{name}", method = RequestMethod.GET)
    String getDynamicUriValueRegex(@PathVariable("name") String name){
    System.out.println("Name is "+name);
    return "Dynamic URI parameter fetched using regex";		
  } 
}
```
Map request using regular expression and request method.     
