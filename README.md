## Mongo Kafka Connector SMT - TimestampConverter

Transform the timestamp of a nested field.  

### Setup
* Build command `mvn clean compile assembly:single`.
* Create a directory in `plugin.path`.
* Add the built jar in the directory created.

### Configuration
```
transforms=TelemetryTimestamp
transforms.TelemetryTimestamp.type=me.rahul.kafka.connect.smt.TimestampConverterWithNestedField$Value
transforms.TelemetryTimestamp.field=fieldName
transforms.TelemetryTimestamp.target.type=Date
transforms.TelemetryTimestamp.zero2null.enable=false
```
Use `transforms.TelemetryTimestamp.zero2null.enable=true` when you are sending timestamp in primitive type `long` and it is `0`, instead of `null`.

### Requirement
* Java 1.8+
* Maven 3
