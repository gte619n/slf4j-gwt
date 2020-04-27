Simple slf4j api implementation for GWT
===

The aim of this project is to provide developers with an implementation of the
[Simple Logging Facade for Java (SLF4J 1.7.30.1)](http://www.slf4j.org/) API for the GWT client side.
Right now the project provides the basic implementation of the SLF4J API using the java.util.logging (JUL)
logging framework supported since [GWT 2.1](http://www.gwtproject.org/). All logging messages are printed to developer/firebug console.
Note that slf4j-gwt depends on the latest stable GWT (GWT 2.8.2).

Source Fork
---
This project is based off of the original library at https://github.com/FinamTrade/slf4j-gwt. Their implementation had fallen behind and had an older GWT dependency. The purpose of this fork is to distribute to maven with the newer GWT 2.8.2 release.

Usage
---
slf4j-gwt is available in [maven central](http://search.maven.org/#artifactdetails%7Ccom.oxos%7Cslf4j-gwt%7C1.7.7.1%7Cjar)

Just include it in your pom.xml
```xml
<dependency>
    <groupId>com.oxos</groupId>
    <artifactId>slf4j-gwt</artifactId>
    <version>1.7.30</version>
</dependency>
```
or gradle build:
```groovy
dependencies {
    compile 'com.oxos:slf4j-gwt:1.7.30'
}
```

or ivy:
```xml
<dependency org="com.oxos" name="slf4j-gwt" rev="1.7.30" />
```

Add dependency in your gwt module descriptor (*.gwt.xml):
```xml
<inherits name="com.oxos.slf4jgwt.logging.gwt.Logging"/>
```

You can also set logging level (ALL, FINEST, FINER, FINE, CONFIG, INFO, WARNING, SEVERE):
```xml
<set-property name="gwt.logging.logLevel" value="INFO"/>
```

Enable or disable gwt logging:
```xml
<set-property name="gwt.logging.enabled" value="TRUE"/>
```

If you want to provide slf4j API (e.g., in library module):
```xml
<inherits name="com.oxos.slf4jgwt.api.API"/>
```

If you want to provide slf4j but to not log anything in your application:
```xml
<inherits name="com.oxos.slf4jgwt.logging.nop.NOP"/>
```

com.oxos.slf4jgwt.logging.util.Util module provides a handful [Log](https://github.com/gte619n/slf4j-gwt/blob/master/src/main/java/com/oxos/slf4jgwt/logging/util/Log.java) class to
log messages without instantiating Logger in client code.
