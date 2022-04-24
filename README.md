# kafka-poc-environment


## Kafkacat

kcat (formerly kafkacat) is a command-line utility that you can use to test and debug Apache Kafka® deployments. You can use kcat to produce, consume, and list topic and partition information for Kafka. Described as “netcat for Kafka”, it is a swiss-army knife of tools for inspecting and creating data in Kafka.


### Producer Mode

In producer mode, kcat reads messages from standard input (stdin). You must specify a Kafka broker (-b) and topic (-t). You can optionally specify a delimiter (-D). The default delimiter is newline.

You can easily send data to a topic using kcat. Run it with the -P command and enter the data you want, and then press Ctrl-D to finish:

```
kcat -b localhost:9092 -t new_topic -P

```

From a container:

```
kcat -b kafka-cp-kafka-headless.kafka -t new_topic -P

```

### Consumer Mode

In consumer mode, kcat reads messages from a topic and partition and prints them to standard output (stdout). You must specify a Kafka broker (-b) and topic (-t). You can optionally specify delimiter (-D). The default delimiter is newline.

You can explicitly specify mode by using the consumer (-C) or producer (-P) flag. You can also specify how many messages you want to see with the lowercase mode identifier and a number (e.g. -c<num>). For example, to consume a single message:

You can supply kcat with a broker (-b) and a topic (-t) and view see its contents:

```
kcat -b localhost:9092 -t new_topic -C
```

From a container:

```
kcat -b kafka-cp-kafka-headless.kafka  -t new_topic -C

```






Sources:

- [Confluent Platform Helm Charts](https://github.com/confluentinc/cp-helm-charts)
- [kcat (formerly kafkacat) Utility](https://docs.confluent.io/platform/current/app-development/kafkacat-usage.html)