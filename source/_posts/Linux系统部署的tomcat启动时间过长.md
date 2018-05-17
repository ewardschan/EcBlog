---
title: Linux系统部署的tomcat启动时间过长
---
tomcat部署的应用启动时间过长问题解决办法。

### 找到:
``` bash
$JAVA_HOME/jre/lib/security/Java.security：
```

### 如果是使用yum默认路径安装的JDK，则:
``` bash
/usr/lib/jvm/java-1.8.0/jre/lib/security/java.security
```

### 将:
``` bash
securerandom.source = file:/dev/random
```

### 或者:
``` bash
securerandom.source = file:/dev/urandom
```

### 修改为：
``` bash
securerandom.source=file:/dev/./urandom
```
