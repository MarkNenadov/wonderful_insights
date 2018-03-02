Java Insights
=================

JUnit
-----

Annotation to make a TestCase class run methods by sorted by name:

```
@FixMethodOrder( MethodSorters.NAME_ASCENDING )

```

Websockets With Spring
----------------------

* How to creator your WebSocketConfigurer:

```
@Configuration
@EnableWebSocket
@ComponentScan( "com.borderconnect.acidirectconnect.websocket" )
public class WebSocketConfiguration implements WebSocketConfigurer {
       public void registerWebSocketHandlers(WebSocketHandlerRegistry registry) {
                registry.addHandler( ... ).setAllowedOrigins( * );
       }
}
```

* How to set your buffer size in Tomcat (put this in your WebSocketConfigurer:

```
    @Bean
    public ServletServerContainerFactoryBean createWebSocketContainer() {
        ServletServerContainerFactoryBean container = new ServletServerContainerFactoryBean();

        container.setMaxTextMessageBufferSize( WEBSOCKET_MAXIMUM_BUFFER_SIZE );
        container.setMaxBinaryMessageBufferSize( WEBSOCKET_MAXIMUM_BUFFER_SIZE );

        return container;
    }
```

JSoup
-----

See java-jsoup.md

Toolkit
-------

* IntelliJ IDEA https://www.jetbrains.com/idea/
* Apache Maven https://maven.apache.org/
* Apache Tomcat
* Spring Framework http://projects.spring.io/spring-framework/
* Spring Boot https://projects.spring.io/spring-boot/
* Web Scrapping http://jsoup.org
* Unit Testing http://junit.org/
* Templating http://freemarker.org/
* Heavy duty ORM http://hibernate.org/
* Lightweight ORM http://ormlite.com/
* PDF http://itextpdf.com	
* Simple Websocket Client/Server http://java-websocket.org/
* JSON (simple parser) http://argo.sourceforge.net/
* JSON (schema validator) https://github.com/fge/json-schema-validator
* DSL for synchronizing asynchronous operations https://github.com/awaitility/awaitility
* Logging http://logging.apache.org/log4j/2.x/
* Markdown Processing http://code.google.com/p/markdown4j/
* Postgres JDBC https://jdbc.postgresql.org/
* Cron Scheduling http://quartz-scheduler.org/
* Apache Ant http://ant.apache.org/
