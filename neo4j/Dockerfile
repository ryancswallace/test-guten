FROM neo4j:5.3.0

# from https://github.com/neo4j-labs/neosemantics
COPY plugins /var/lib/neo4j/plugins
COPY conf /var/lib/neo4j/conf

ENV NEO4J_AUTH=none

ENV http_proxy=http://a1proxy.frb.org:8080
ENV https_proxy=http://a1proxy.frb.org:8080
ENV no_proxy=frb.org,frb.pvt,frb.gov,frbres.org,frgb.gov,base.awscfs.frb.pvt,localhost,10.0.0.0/8,172.16.0.0/12,192.168.0.0/16,127.0.0.1

RUN apt-get update && apt-get -y install curl

EXPOSE 7474
EXPOSE 7687

ENTRYPOINT ["neo4j"]
CMD ["console"]

# sudo docker build -t guten-neo .
# sudo docker run --name guten-neo -d --publish=7474:7474 --publish=7687:7687 -v $HOME/test-guten/neo4j/import:/var/lib/neo4j/import guten-neo
# sudo docker exec -it guten-neo  /bin/bash

# doesn't work: curl -H "Content-Type: application/json" -X POST -d '{"password":"test123!"}' -u neo4j:test1234! http://localhost:7474/user/neo4j/password

# wget https://www.gutenberg.org/cache/epub/feeds/rdf-files.tar.bz2
# bunzip2 rdf-files.tar.bz2
# tar xf rdf-files.tar

# cypher-shell -u neo4j -p test1234!
# CREATE CONSTRAINT n10s_unique_uri FOR (r:Resource) REQUIRE r.uri IS UNIQUE;
# CALL n10s.graphconfig.init();
# CALL n10s.rdf.import.fetch('file:///var/lib/neo4j/import/cache/epub/23081/pg23081.rdf', 'RDF/XML');


# TODO:
# auth
# persistent volume option for data
# overlay network for compose
# remove vim