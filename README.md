## Mongo Kafka Connector SMT - TimestampConverter

Transform the timestamp of a nested field.  

### Setup
* Build command `mvn clean compile assembly:single`.
* Create a directory in `plugin.path`.
* Add the built jar in the directory created.

### Configuration
```
transforms=MyTransform
transforms.MyTransform.type=me.rahul.kafka.connect.smt.TimestampConverterWithNestedField$Value
transforms.MyTransform.field=fieldName
transforms.MyTransform.target.type=Date
transforms.MyTransform.zero2null.enable=false
```
Use `transforms.MyTransform.zero2null.enable=true` when you are sending timestamp in primitive type `long` and it is `0`, instead of `null`.

### Requirement
* Java 1.8+
* Maven 3
