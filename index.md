---
layout: default
---

### Stubbed Cassandra

Developing software is fun. Developing software that is well tested, where those tests run quickly is even more fun.

Stubbed Cassandra is an open source tool that enables you to test applications that use Cassandra in a quick, deterministic way.

It is especially aimed edge case testing such as read and write timeouts.

It acts as a real Cassandra instance and can be primed to respond with results or with exceptions like read timeouts. It does this by implementing the server side of the CQL binary protocol.

It is separated into two components:

* [Scassandra Server](/scassandra-server): Stubbed Scassandra server. Implemented in Scala, can be run as a standalone server or depended on via the Java client. Doesn't have an embedded Cassandra, is a standalone implementation of the server side of the Cassandra native protocol. You can prime the server to return rows, read timeout and write timeout via a REST API.
* [Java Client](/java-client): Java client for Scassandra. A thin Java wrapper around Scassandra that allows Java projects to depend on Scassandra via maven dependency and have a programmatic interface for starting/stopping and priming.

The first version of Scassandra, v0.1, is aimed at Java developers so most of the information is on the Java Client section of the website.
The next version will focus on running Scassandra standalone.

###Features v0.1:
* Priming of queries with columns of all the primitive types (no suport for collections/custom tyes).
* Priming of prepared statements. The variable (?s) types and response types can be any of the primitive types.
* Retrieval of a list of all recorded queries.
* Retrieval of a list of all the recorded executed prepared statements. If the prepared statement has been primed then the variable values are also visible.

###Feature backlog:
* Retrieval of a list of all prepared statements even if they haven't been executed.
* Priming of tables rather than queries. Currently Scassandra does not parse the query and compares an executed query with all the primes query field. This would be very useful for priming the system keyspace as certain drivers expect the same thing to be in system.local but do slightly different queries to retireve it.


###Current limitations:
* Only tested with Java Datastax driver version 2 and above. Support for version 1 will come later. Other drivers will be tested and supported soon.
* Collections aren't supported.
* Custom types aren't supported.
* Binary protocol only. No planned support for thrift.

For feature requests and bug reports send an email to: Christopher.batey@gmail.com

### Authors 
* Christopher Batey (@chbatey)
* Dogan Narinc

