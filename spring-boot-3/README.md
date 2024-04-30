El kell dobni az adatbázist!

```yaml
    jpa:
    hibernate:
      ddl-auto: none
    properties:
      hibernate:
        order_inserts: true
        order_updates: true
        timezone:
          default_storage: NORMALIZE_UTC
        jdbc:
          batch_size: 1000
          fetch_size: 1000
          batch_versioned_data: true
```

### Releases
##### #1 commit

###### Feature:
1. **Spring Boot 3**

````xlm
    <dependency>
        <groupId>hu.mavir.boss</groupId>
        <artifactId>timeseries-jpa</artifactId>
        <version>2.0.0-SNAPSHOT</version>
    </dependency>
````

This bean needs to be created:
````java
    @Bean
    public Definitions definitions() {
        Definitions t = new Definitions();
        t.register(Labels.ta);
        t.register(Labels.siteId);
        return t;
    }
````

