# Replication And Consistency(Not Consensus)

在分布式系统中，复制可用来实现Reliable, Scalable. 数据的复制会导致一致性问题。 数据的复制也即同步过程，会带来节点是否可用问题，这也是CAP中的AP权衡。
复制是一项基础技术，而一致性是这项技术带来的问题。可以认为没有复制便没有一致性问题。

PacificA: Replication in Log-Based Distributed Storage Systems

Replication in database,kv,document-db,column-db,file system, distributed coordination,framework

Replication Model https://en.wikipedia.org/wiki/Replication_(computing)

Consistency Model https://en.wikipedia.org/wiki/Consistency_model

Consistency Model https://jepsen.io/consistency


## 复制的基本问题

1. 复制方式：主从，多主，无主
2. 同步还是异步
3. 处理失败副本
4. 数据滞后问题


## 关键词

data replication

## Paper

Understanding Replication in Databases and Distributed Systems

A Suite of Database Replication Protocols based on group communication

Chain Replication for Supporting High Throughput and Availability

## 重点研究

MySQL，PostgreSQL，Kafka，Redis，

## Database

mysql  https://dev.mysql.com/doc/refman/8.0/en/replication.html

postgresql  https://www.postgresql.org/docs/current/high-availability.html

mariadb https://mariadb.com/kb/en/standard-replication/

## KV store

redis  https://redis.io/topics/replication

etcd https://etcd.io/docs/v3.3/faq/

riak https://docs.riak.com/riak/kv/latest/learn/concepts/replication/index.html

tikv: https://tikv.org/deep-dive/scalability/introduction/

dynamo:https://www.allthingsdistributed.com/files/amazon-dynamo-sosp2007.pdf

consul  https://www.consul.io/docs/architecture

## Document

mongodb https://docs.mongodb.com/manual/replication/

couchdb https://docs.couchdb.org/en/stable/replication/intro.html
https://guide.couchdb.org/editions/1/en/replication.html

## Framework

hazelcast  https://docs.hazelcast.com/imdg/4.2/consistency-and-replication/consistency

akka https://doc.akka.io/docs/akka/current/typed/cluster-concepts.html

## Column DB

cassandra  https://cassandra.apache.org/doc/latest/cassandra/architecture/overview.html

hbase https://hbase.apache.org/book.html#_cluster_replication

## Message

kafka https://kafka.apache.org/documentation/#replication

https://cwiki.apache.org/confluence/display/kafka/kafka+replication

rabbitmq https://www.rabbitmq.com/ha.html

rocketmq https://rocketmq.apache.org/docs/rmq-deployment/

activemq https://activemq.apache.org/clustering

## Search

elasticsearch https://www.elastic.co/guide/en/elasticsearch/reference/current/modules-discovery.html

solr https://solr.apache.org/guide/6_6/index-replication.html

## File System

hdfs https://hadoop.apache.org/docs/r1.2.1/hdfs_design.html#Data+Replication

ceph https://ceph.io/assets/pdfs/weil-crush-sc06.pdf

GFS https://static.googleusercontent.com/media/research.google.com/zh-CN//archive/gfs-sosp2003.pdf

## Coordination

zookeeper: https://zookeeper.apache.org/doc/r3.2.2/zookeeperInternals.html

## Distributed database(newsql)

yugabyte https://docs.yugabyte.com/latest/architecture/docdb-replication/replication/

CockroachDB  https://www.cockroachlabs.com/docs/stable/architecture/replication-layer.html

TiDB https://docs.pingcap.com/tidb/stable/bidirectional-replication-between-tidb-clusters   

## other

Aurora https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/Aurora.Replication.html

Spanner/F1

rethinkdb https://rethinkdb.com/docs/architecture/

Windows Azure Storage https://docs.microsoft.com/en-us/azure/storage/common/storage-redundancy

voldemort  https://www.project-voldemort.com/voldemort/design.html

Bigtable https://static.googleusercontent.com/media/research.google.com/zh-CN//archive/bigtable-osdi06.pdf

Yahoo PNUTS https://sites.cs.ucsb.edu/~agrawal/fall2009/PNUTS.pdf

VoltDB https://docs.voltdb.com/UsingVoltDB/ChapReplication.php

ScyllaDB https://docs.scylladb.com/architecture/

foundationdb: https://apple.github.io/foundationdb/consistency.html

https://apple.github.io/foundationdb/fault-tolerance.html

## Compute

Flink:

Spark:

Storm:


| Application | Replication Model | Consistency Model |
| ----------- | ----------------- | ----------------- |
|             |                   |                   |
|             |                   |                   |
|             |                   |                   |

