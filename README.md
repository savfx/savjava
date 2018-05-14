
```java

package com.sav.myApi.schema

public class ResHomeIndex {
    public String name;
}

public class ReqHomeIndex {
    public Integer id;
}

```

```java
package com.sav.myApi.router

@Modal(
    path="/"
)
public @interface HomeInterface {
    @get(
        path="/:index?"
    )
    public ResHomeIndex index(ReqHomeIndex input) {}
}

```

```java

package com.service.controller

public class HomeController implements HomeInterface {
    public ResHomeIndex index(ReqHomeIndex input)
    {
        ResHomeIndex res;
        res.name = "test";
        return res;
    }
}

```

```java

package com.client.controller

public class ClientController {
    public void index()
    {
        ReqHomeIndex req;
        req.id = 0;
        ResHomeIndex res = this.myApi.fetch(req)
    }
}

```
