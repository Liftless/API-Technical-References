The OAuth 2.0 Authorization Framework - Reference
-------------------------------------------------

[RFC6749](https://datatracker.ietf.org/doc/html/rfc6749) The OAuth 2.0 Authorization Framework

### Roles

[Roles](https://datatracker.ietf.org/doc/html/rfc6749#section-1.1)

- Resource owner: the user
- Resource server: the API
- Authorization server: can be the same server as the API
- Client: the application

### Protocol Flow

[Protocol Flow](https://datatracker.ietf.org/doc/html/rfc6749#section-1.2)

```
+--------+                               +---------------+
|        |--(A)- Authorization Request ->|   Resource    |
|        |                               |     Owner     |
|        |<-(B)-- Authorization Grant ---|               |
|        |                               +---------------+
|        |
|        |                               +---------------+
|        |--(C)-- Authorization Grant -->| Authorization |
| Client |                               |     Server    |
|        |<-(D)----- Access Token -------|               |
|        |                               +---------------+
|        |
|        |                               +---------------+
|        |--(E)----- Access Token ------>|    Resource   |
|        |                               |     Server    |
|        |<-(F)--- Protected Resource ---|               |
+--------+                               +---------------+
```

<!-- END -->