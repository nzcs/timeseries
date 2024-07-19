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
          default_storage: NORMALIZE
        jdbc:
          time_zone: UTC
          batch_size: 1000
          fetch_size: 1000
          batch_versioned_data: true
```

### Releases

###### Feature:
1. **Spring Boot 3 RHU**

````xlm
    <dependency>
            <groupId>hu.mavir.boss</groupId>
            <artifactId>timeseries-core</artifactId>
            <version>2.0.0-RHU-SNAPSHOT</version>
            <scope>system</scope>
            <systemPath>
                ${project.basedir}/src/main/resources/webapp/WEB-INF/lib/timeseries-core-2.0.0-RHU-SNAPSHOT.jar
            </systemPath>
        </dependency>
        
        <dependency>
            <groupId>hu.mavir.boss</groupId>
            <artifactId>timeseries-qdsl</artifactId>
            <version>2.0.0-RHU-SNAPSHOT</version>
            <scope>system</scope>
            <systemPath>
                ${project.basedir}/src/main/resources/webapp/WEB-INF/lib/timeseries-qdsl-2.0.0-RHU-SNAPSHOT.jar
            </systemPath>
        </dependency>
        
        <dependency>
            <groupId>hu.mavir.boss</groupId>
            <artifactId>timeseries-jpa</artifactId>
            <version>2.0.0-RHU-SNAPSHOT</version>
            <scope>system</scope>
            <systemPath>
                ${project.basedir}/src/main/resources/webapp/WEB-INF/lib/timeseries-jpa-2.0.0-RHU-SNAPSHOT.jar
            </systemPath>
        </dependency>
````
