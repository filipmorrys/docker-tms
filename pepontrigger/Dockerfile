FROM cassandra:4.0.1


COPY cassandra-trigger-lib-6.0.0.jar $CASSANDRA_HOME/conf/triggers
COPY InvertedIndex.properties $CASSANDRA_HOME/conf

# 7000: intra-node communication
# 7001: TLS intra-node communication
# 7199: JMX
# 9042: CQL
EXPOSE 7000 7001 7199 9042

ENTRYPOINT "docker-entrypoint.sh" && "/opt/cassandra/bin/cassandra" "-Rf" && "/opt/cassandra/bin/nodetool reloadtriggers"