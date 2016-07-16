# High-level

1. Talks about stream processing pipeline design choice at Facebook
2. Certain typical stream processing use cases at Facebook
3. Does not go into the streaming system implementation details
  1. Puma - SQL-like stream processing DSL
  2. Swift - low-level, stateless processing. Includes checkpointing.
  3. Stylus - stream processing framework. Think Samza. Supports stateful processing
  4. Laser - KV Storage service built on RocksDB. Can ingest from from Scribe or Hive periodically. Used for state and serving layer.
  5. Scribe - message bus. Think Kafka. Durability by storing to HDFS.
4. Like a survey on stream processing framework(discuss on alternative choices)
  1. Lanuage paradigm
  2. Data transfer(messaging queue choice)
  3. Processing semantics
  4. State-saving mechanisms
  5. Backfill processing

Overall it is easy to match the design with Kafka+Samza.


References:
- https://research.facebook.com/publications/realtime-data-processing-at-facebook/
- https://blog.acolyer.org/2016/07/11/realtime-data-processing-at-facebook/
