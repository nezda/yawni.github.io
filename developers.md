---
layout: page
title: Developers
description: Developers
---
Browse the source code online, or clone [the Github repository](https://github.com/nezda/yawni):

```
git clone git@github.com:nezda/yawni.git
```

Building the project is easy with our Apache Maven -based build; just clone the repository, and

```
mvn clean install
```

To use Yawni, you must include its core api jar file in your classpath; this is easiest with a Maven dependency:

```xml
<dependency>
  <groupId>org.yawni</groupId>
  <artifactId>yawni-wordnet-api</artifactId>
  <version>{{ site.data.yawni.version }}</version>
</dependency>
```

Yawni also includes optional jar files containing all the data from WordNet version 3.0 (and 2. and 2.1) which simplifies deployment (e.g., client doesn't need to download WordNet, export environment variables, etc.); this Maven dependency is all you need:

```xml
<dependency>
  <groupId>org.yawni</groupId>
  <artifactId>yawni-wordnet-data30</artifactId>
  <version>{{ site.data.yawni.version }}</version>
</dependency>
```

To integrate Yawni into your project, you'll need to choose the [SLF4J](https://www.slf4j.org/) logging implementation that is compatible with your project's logging: all this requires is adding a small jar    file to your classpath, and you can automate this with a Maven dependency. For example:

If your project doesn't use logging, add this to your pom.xml:

```xml
<dependency>
  <groupId>org.slf4j</groupId>
  <artifactId>slf4j-nop</artifactId>
  <version>{{ site.data.yawni.slf4j_version }}</version>
</dependency>
```

If your project uses java.util.logging, add this to your pom.xml:

```xml
<dependency>
  <groupId>org.slf4j</groupId>
  <artifactId>slf4j-jdk14</artifactId>
  <version>{{ site.data.yawni.slf4j_version }}</version>
</dependency>
```

If your project uses log4j, add this to your pom.xml:

```xml
<dependency>
  <groupId>org.slf4j</groupId>
  <artifactId>slf4j-log4j12</artifactId>
  <version>{{ site.data.yawni.slf4j_version }}</version>
</dependency>
```

A more detailed explanation can be found at [https://mina.apache.org/logging-configuration.html](https://mina.apache.org/logging-configuration.html) or in the [SLF4J manual](http://www.slf4j.org/manual.html).