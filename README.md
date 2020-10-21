# nifi-cassandra-3.10.2
 NiFi 1.12.1 Cassandra Core Driver Version 3.10.2

In order to connect NiFi to Astra with Native NiFi Cassandra Drivers (PutCassandraQL, PutCassandraRecord, QueryCassandra) we must update the cassandra driver core from 3.3.0 to 3.10.2.  This is easily done by unpacking the source nar files, adjusting the dependencies to include the new cassandra driver core, and rebuilding the nar.  Follow the instructions below to update NiFi drivers.

# In This Repo
- Original NiFi 1.12.1 Cassandra NARs
- Updated NiFi 1.12.1 Cassandra NARs
- META-INF source folder for each NAR

# Important Differences
- https://mvnrepository.com/artifact/com.datastax.cassandra/cassandra-driver-core/3.10.2
```
<!-- https://mvnrepository.com/artifact/com.datastax.cassandra/cassandra-driver-core -->
<dependency>
    <groupId>com.datastax.cassandra</groupId>
    <artifactId>cassandra-driver-core</artifactId>
    <version>3.10.2</version>
</dependency>
```
- Above dependency added to each NARs pom.xml file

# NiFi Installation Instructions
Be sure to compelete these steps on all NiFi nodes in your NiFi cluster.
- Stop NiFi
- Replace drivers with updated drivers in nifi /lib folder
- Remove nifi /work folder
- Restart NiFi