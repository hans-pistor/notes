+++
title = "@ConfigurationProperties"
author = ["Hans Pistor"]
date = 2021-01-18T11:22:00-05:00
tags = ["java", "spring"]
draft = false
+++

You can embed configuration properties inside a POJO using this annotaiton. Must add @EnableConfigurationProperties in one of the Configuration classes, otherwise this annotation won't work.

```java
@Component
@ConfigurationProperties(prefix="accounts.client")
public class ConnectionSettings {
    private String host;
    private int port;
    private String logDir;
    private int timeout;

    // getters & setters
}
```

is the same as

```yaml
accounts.client.host=
accounts.client.port=
accounts.client.logDir=
accounts.client.timeout=

```


## Links to this note {#links-to-this-note}

-   [Automatic Configuration]({{< relref "20210118105735-automatic_configuration" >}})
