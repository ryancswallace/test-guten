FROM neo4j:5.3.0

# from https://github.com/neo4j-labs/neosemantics
COPY plugins /var/lib/neo4j/plugins
COPY conf /var/lib/neo4j/conf

ENV NEO4J_AUTH=none

EXPOSE 7474
EXPOSE 7687

ENTRYPOINT ["neo4j"]
CMD ["console"]

# CREATE CONSTRAINT n10s_unique_uri FOR (r:Resource) REQUIRE r.uri IS UNIQUE
# CALL n10s.graphconfig.init()
# CALL n10s.rdf.import.fetch('file:///var/lib/neo4j/import/cache/epub/23081/pg23081.rdf', 'RDF/XML');


# TODO:
# auth
# persistent volume option for data
# overlay network for compose
# remove vim