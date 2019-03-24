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
