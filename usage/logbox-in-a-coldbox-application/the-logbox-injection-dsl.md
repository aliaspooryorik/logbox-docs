# The LogBox Injection DSL

WireBox DI and Injection can talk to LogBox. This way you can easily use our dependency injection DSL for LogBox related objects:

| Type                     | Description                                                                                  |
| ------------------------ | -------------------------------------------------------------------------------------------- |
| `logbox`                 | Get a reference to the application's LogBox instance                                         |
| `logbox:root`            | Get a reference to the root logger                                                           |
| `logbox:logger:category` | Get a reference to a named logger by its category name                                       |
| `logbox:logger:{this}`   | Get a reference to a named logger according to the current class path of the injected target |

Below you can see the most common usage of this dependency DSL:

```javascript
//  LogBox wired in
property name="logBox" inject="logbox";

//  Root Logger
property name="logger" inject="logbox:root";

//  Named Category
property name="logger" inject="logbox:logger:com.api.model";

//  Category eq to ClassPath
property name="logger" inject="logbox:logger:{this}";
```
