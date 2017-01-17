---
layout: default
---

### Stubbed Cassandra

Developing software is fun. Developing software that is well tested, where those tests run quickly is even more fun.

Stubbed Cassandra is an open source tool that enables you to test applications that use Cassandra in a quick, deterministic way.

It is especially aimed edge case testing such as read and write timeouts.

It acts as a real Cassandra instance and can be primed to respond with results or with exceptions like read timeouts. It does this by implementing the server side of the CQL binary protocol.

It is separated into two components:

* [Java Client](http://scassandra-docs.readthedocs.org/en/latest/java/overview/): Java client for Scassandra. A thin Java wrapper around Scassandra that allows Java projects to depend on Scassandra via maven dependency and have a programmatic interface for starting/stopping and priming.
* [Scassandra Server](http://scassandra-docs.readthedocs.org/en/latest/standalone/overview/): Stubbed Scassandra server. Only go here if you're insterested in running Stubbed Cassandra without a build tool such as maven or gradle. Implemented in Scala, can be run as a standalone server or depended on via the Java client. Doesn't have an embedded Cassandra, is a standalone implementation of the server side of the Cassandra native protocol. You can prime the server to return rows, read timeout and write timeout via a REST API.

Scassandra, currently v1.1.0, is aimed at Java developers so most of the information is on the Java Client section of the website.  It also may be used as a standalone jar.

###Release v1.1.1
* [#181](https://github.com/scassandra/scassandra-server/issues/181) - Record 'USE <keyspace>' queries in activity log

###Release v1.1.0
* [#171](https://github.com/scassandra/scassandra-server/pull/171) - Protocol 3 and 4 support.  Migrate cql-antlr into tree as submodule.

###Release v1.0.10
* [#167](https://github.com/scassandra/scassandra-server/pull/167) - Provide CORS support to Scassandra endpoints

###Release v1.0.9
* [#157](https://github.com/scassandra/scassandra-server/pull/157) - Share ActorSystem between Scassandra instances

###Release v1.0.8
* [#155](https://github.com/scassandra/scassandra-server/pull/155) - Add getters for thens in multi-prime requests

###Release v1.0.7
* [#151](https://github.com/scassandra/scassandra-server/pull/151) - Allow priming of config using config object
* [#154](https://github.com/scassandra/scassandra-server/pull/154) - Provide custom configuration for batch result

###Release v1.0.6
* [#149](https://github.com/scassandra/scassandra-server/pull/149) - Introduce alias for Then to avoid reserved word issues 
* [#150](https://github.com/scassandra/scassandra-server/pull/150) - Handle invalid types with an informative error message

###Release v1.0.5
* [#148](https://github.com/scassandra/scassandra-server/pull/148) - Use shapeless 2

###Release v1.0.4
* [#147](https://github.com/scassandra/scassandra-server/pull/147) - Akka configuration fix

###Release v1.0.3
* [#141](https://github.com/scassandra/scassandra-server/pull/141) - Add ability to retrieve prepared multi primes

###Release v1.0.2
* [#140](https://github.com/scassandra/scassandra-server/pull/140) - Support for clearing prepared multi primes

###Release v1.0.1
* [#139](https://github.com/scassandra/scassandra-server/pull/139) - Delay support for batch statements

###Release v1.0.0
* Multi prime API.

###Release v0.11.0
* Log better error message for timeout binding to ports
* [#112](https://github.com/scassandra/scassandra-server/issues/112) - Prime Result that closes connection
* [#115](https://github.com/scassandra/scassandra-server/pull/115) - Archive standalone jar

###Release v0.10.0
* Batch support
* Ability to see currently connected clients and kill connections

###Release v0.9.1
* Java 6 suppport for those still sadly using it
* Verification for when a prepared statement is prepared
* Fat jar support
* Capturing of query parameters for non-prepared statements

###Release v0.8.0
* Noving to a single build for server, client and tests.

###Release v0.7.0: 
* Support for priming specific errors e.g the number of replicas responded rather than just that it wsa a read/write timeout
* Removed support for version 1.* of the Java DataStax driver due to classpath issues (you can still use 2.* with Cassandra 1.2 and it will work)

###Release v0.6.0: 
* Support for maps of any type
* New method for priming types: CqlType (the ColumnTypes enum has been deprecated)
* Prepared statement matcher now handles maps
 
###Release v0.5.0: 
* Support for lists and sets of any type
* Prepared statement matcher that handles matching the varialbe list correctly

###Release v0.4.1
* [Feature #50] Support adding a fixed delay to both queries and prepared statements
* [Feature #52] Cassandra 2.1 support
* [Feature #53] JUnit matchers for queries and prepared statements

###Release v0.3.0
* Text map maps support: varchar, ascii and text
* Can use a queryPattern rather than a query for priming, making knowing the exact query the application will execute no longer necessary
* [Bug #49] QueryPattern for prepared statements for error scenarios do not work

###Release v0.2.0
* Lists and sets of the character types: varchar, ascii and text
* JUnit rule for Java Client

###Release v0.1:
* Priming of queries with columns of all the primitive types (no suport for collections/custom tyes).
* Priming of prepared statements. The variable (?s) types and response types can be any of the primitive types.
* Retrieval of a list of all recorded queries.
* Retrieval of a list of all the recorded executed prepared statements. If the prepared statement has been primed then the variable values are also visible.

###Feature backlog:
* User defined types
* Batches
* Retrieval of a list of all prepared statements even if they haven't been executed.
* Priming of tables rather than queries. Currently Scassandra does not parse the query and compares an executed query with all the primes query field. This would be very useful for priming the system keyspace as certain drivers expect the same thing to be in system.local but do slightly different queries to retireve it.

For feature requests and bug reports raise an issue at the [Github issues page](https://github.com/scassandra/scassandra-server/issues)

Any questions ping me on twitter: @chbatey

### Authors 
* Christopher Batey (@chbatey)
* Dogan Narinc

