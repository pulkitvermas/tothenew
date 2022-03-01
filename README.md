# Maven

##### Compile:
This is the default scope when no other scope is provided.Dependencies with this scope are available on the classpath of the project in all build tasks. They are also propagated to the dependent projects. More importantly, these dependencies are also transitive:
```
<dependency>
    <groupId>commons-lang</groupId>
    <artifactId>commons-lang</artifactId>
    <version>2.6</version>
</dependency>
```

##### Runtime:
The dependencies with this scope are required at runtime. But we don't need them for compilation of the project code. Because of that, dependencies marked with the runtime scope will be present in the runtime and test classpath, but they will be missing from the compile classpath.
```
<dependency>
    <groupId>mysql</groupId>
    <artifactId>mysql-connector-java</artifactId>
    <version>6.0.6</version>
    <scope>runtime</scope>
</dependency>
```

##### Test:
We use this scope to indicate that dependency isn't required at standard runtime of the application but is used only for test purposes.
Test dependencies aren't transitive and are only present for test and execution classpaths.
The standard use case for this scope is adding a test library such as JUnit to our application:
```
<dependency>
    <groupId>junit</groupId>
    <artifactId>junit</artifactId>
    <version>4.12</version>
    <scope>test</scope>
</dependency>
```

##### Provided:
We use this scope to mark dependencies that should be provided at runtime by JDK or a container.
A good use case for this scope would be a web application deployed in some container, where the container already provides some libraries itself. For example, this could be a web server that already provides the Servlet API at runtime.
```
<dependency>
    <groupId>javax.servlet</groupId>
    <artifactId>servlet-api</artifactId>
    <version>2.5</version>
    <scope>provided</scope>
</dependency>
```
