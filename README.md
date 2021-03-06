Solandra
========
Solandra is a real-time distributed search engine built on [Apache Solr](http://lucene.apache.org) and [Apache Cassandra](http://cassandra.apache.org).

At its core Solandra is a tight integration of Solr and Cassandra, meaning within a single JVM both Solr and Cassandra are running, and 
documents are stored and disributed using Cassandra's data model. 

Solandra makes managing and dynamically growing Solr simple(r). 

For more information please see the [wiki](https://github.com/tjake/Lucandra/wiki)

####Requirements:####

Java >= 1.6

####Features:######

  - Supports most out-of-the-box Solr functionality (search, faceting, highlights)
  - Replication, Sharding, Caching and Compaction managed by Cassandra
  - Multi-master (read/write to any node)
  - Writes become available as soon as write succeeds
  - Easily add new SolrCores w/o restart across the cluster 

####Getting started:####

The following will guide you through setting up a single node instance of Solandra.

From the Solandra base directory:
  
  - mkdir /tmp/cassandra-data
  - ant
  - cd solandra-app; ./start-solandra.sh -b #(-b adds the solandra specific cassandra schema)
  
Now that Solandra is running you can run the demo:
  
  - cd ../../reuters-demo
  - ./1-download_data.sh
  - ./2-import_data.sh  
  - While data is loading open the file ./website/index.html in your favorite browser 


####Limitations####

Solandra uses Solr's built in distributed searching meachanism, 
most of it's limitations covered here: 

[http://wiki.apache.org/solr/DistributedSearch#Distributed_Searching_Limitations](http://wiki.apache.org/solr/DistributedSearch#Distributed_Searching_Limitations)