El kell dobni az adatbázist!

```yaml
  jpa:
    hibernate:
      ddl-auto: none
    properties:
      hibernate:
        order_inserts: true
        order_updates: true
        jdbc:
          time_zone: UTC
          batch_size: 1000
          fetch_size: 1000
          batch_versioned_data: true
```