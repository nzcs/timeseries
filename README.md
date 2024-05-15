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

### Releases
##### #35 commit

labels: "!oracle_ee"


##### #34 commit
javax.persistence.lock.timeout => 10min

##### #24 commit
###### Bug fix:
1. Pessimistic write locking in TimeSeries

###### Feature:
1. Added new function: **integral**

example:
````java
TimeSeriesModel ts = TimeSeriesModel.builder()
    .definition(name, "name_A")
    .timeSeries(timeSeries(parse("2023-05-20 00:00"), QUARTER_HOURLY, 1, 1, 1, 1, 2, 2, 2, 2))
.build();

TimeSeriesModel result = ts.integral(HOURLY);

result itms: [4, 8]
````

2. Added new function: **append**

example:
````java
append(
    TimeSeriesModel.builder()
        .definition(name, "name_A")
        .definition(type, RTB)
        .timeSeries(timeSeries(parse("2023-05-20 00:00"), HOURLY, 1, 2, GAP, 4, GAP, GAP, GAP))
    .build()
);

append(
    TimeSeriesModel.builder()
        .definition(name, "name_A")
        .definition(type, RTB)
        .timeSeries(timeSeries(parse("2023-05-20 01:00"), HOURLY, 2.1, 3.1, GAP, GAP, 6))
    .build()
);

append(
    TimeSeriesModel.builder()
        .definition(name, "name_A")
        .definition(type, RTB)
        .timeSeries(timeSeries(parse("2023-05-20 06:00"), HOURLY, 7))
    .build()
);

// then
TimeSeriesModel.builder()
    .definition(name, "name_A")
    .definition(type, RTB)
    .item(parse("2023-05-20 00:00"), 1, 1)
    .item(parse("2023-05-20 01:00"), 2.1, 2)
    .item(parse("2023-05-20 02:00"), 3.1, 1)
    .item(parse("2023-05-20 03:00"), GAP, 2)
    .item(parse("2023-05-20 04:00"), GAP, 1)
    .item(parse("2023-05-20 05:00"), 6, 1)
    .item(parse("2023-05-20 06:00"), 7, 1)
    .build()
    .setVersion(3);
````