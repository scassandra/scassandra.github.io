---
layout: default
---

### Stubbed Cassandra

Developing software is fun. Developing software that is well tested, where those tests run quickly is even more fun. Stubbed Cassandra allows you to test your applications that use Cassandra in a quick, deterministic way.

It is separated into two components:

* [Scassandra Server](/scassandra-server): Stubbed Scassandra server. Implemented in Scala, can be run as a standalone server or depended on via the Java client. Doesn't have an embedded Cassandra, is a standalone implementation of the server side of the Cassandra native protocol. You can prime the server to return rows, read timeout and write timeout via a REST API.
* [Java Client](/java-client): Java client for Scassandra. A thin Java wrapper around Scassandra that allows Java projects to depend on Scassandra via maven dependency and have a programmatic interface for starting/stopping and priming.

### Authors 
* Christopher Batey (@chbatey)
* Dogan Narinc

