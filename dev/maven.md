Maven Insights
=================

Find potential updates
----------------------

```
versions:display-dependency-updates
```

Build fat JAR (with dependencies included)
------------------------------------------

Single JAR, with the name of the project

```
            <plugin>
                <artifactId>maven-jar-plugin</artifactId>
                <version>3.0.2</version>
                <executions>
                    <execution>
                        <id>default-jar</id>
                        <phase>none</phase>
                    </execution>
                </executions>
            </plugin>
            <plugin>
                <artifactId>maven-assembly-plugin</artifactId>
                <executions>
                    <execution>
                        <phase>package</phase>
                        <goals>
                            <goal>single</goal>
                        </goals>
                    </execution>
                </executions>
                <configuration>
                    <descriptorRefs>
                        <descriptorRef>jar-with-dependencies</descriptorRef>
                    </descriptorRefs>
                    <finalName>${project.name}</finalName>
                    <appendAssemblyId>false</appendAssemblyId>
                </configuration>
            </plugin>
```

Two JARs: one regular name without dependencies, one with dependencies and "jar-with-dependencies" appended.

```
            <plugin>
                <artifactId>maven-assembly-plugin</artifactId>
                <executions>
                    <execution>
                        <phase>package</phase>
                        <goals>
                            <goal>single</goal>
                        </goals>
                    </execution>
                </executions>
                <configuration>
                    <descriptorRefs>
                        <descriptorRef>jar-with-dependencies</descriptorRef>
                    </descriptorRefs>
                </configuration>
            </plugin>
```
