High-level

# Talks about stream processing pipeline design choice at Facebook
# Certain typical stream processing use cases at Facebook
# Does not go into the streaming system implementation details
## Puma - SQL-like stream processing DSL
## Swift - low-level, stateless processing. Includes checkpointing.
## Stylus - stream processing framework. Think Samza. Supports stateful processing
### Laser - KV Storage service built on RocksDB. Can ingest from from Scribe or Hive periodically. Used for state and serving layer.
## Scribe - message bus. Think Kafka. Durability by storing to HDFS.
# Like a survey on stream processing framework(discuss on alternative choices)
## Lanuage paradigm
## Data transfer(messaging queue choice)
## Processing semantics
## State-saving mechanisms
## Backfill processing

Overall it is easy to match the design with Kafka+Samza.


References:
- https://research.facebook.com/publications/realtime-data-processing-at-facebook/
- https://blog.acolyer.org/2016/07/11/realtime-data-processing-at-facebook/
