# cloudera-eap-modules
JBoss EAP 6.x static Modules for Hadoop Cloudera

about the modules:

#public and private modules
accordingly with JBoss EAP modules' standards, the third party modules as 
dependency of the cloudera main modules as the same as some cloudera modules 
has been defined as Private.
The cloudera JBoss modules referenceable by enterprise applications, instead, 
has been defined as public.

#public modules list:
yarn-client
hdfs
impala (3 different versions, depending of what bug you like to deal with :-) )
phoenix (not supported by cloudera 5.3, but stable upstream version)
hive
solr

#private cloudera modules  
hadoop-commons
hadoop-annotations
hadoop auth
zookeeper

#some considerations about third party modules
jersey - hadoop commons needs jersey in order to support most of the servers 
         playing a relevant role into the cloudera ecosystem. 
         Jersey, moreover, is an implementation of the JaxRS spec. Because of 
         this, in order to make your JBoss EAP enterprise application work, 
         it is possible to disable resteasy jboss subsystem or reference the 
         jersey module using the attributes "services exclude" (this kind of 
         approach has been preferred to the forst one).  

I'll commit some enterprise applications for test purposes. Meanwhile, if you 
want to test theese modules by yourself, I suggest to download the cloudera 
test VM and follow this guide in order to install a local KDC server and client:

https://developer.jboss.org/wiki/SetupKDCForKerberosTesting

 