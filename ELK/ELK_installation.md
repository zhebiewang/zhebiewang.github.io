# Install ELK Cluster

## Create Folder

- cd /home


- mkdir wangjie


- cd wangjie


- mkdir downloads


- cd downloads

##unzip

```
- tar zxvf elasticsearch-5.4.1.tar.gz -C ..

- tar zxvf logstash-5.4.1.tar.gz  -C ..

- tar zxvf kibana-5.4.2-linux-x86_64.tar.gz -C..

- tar zxvf jdk-8u131-linux-x64.tar.gz -C ..

```

##Config Elasticsearch

Host:XXX.XXX.XXX.161

- network.host: XXX.XXX.XXX.161


- cluster.name: bigdatagroup.com


- node.name: n1.bigdatagroup


- http.port: 9200


- bootstrap.memory_lock: false 


- bootstrap.system_call_filter: false


- discovery.zen.ping.unicast.hosts: ["XXX.XXX.XXX.115", "XXX.XXX.XXX.179"]


- ​

Host: XXX.XXX.XXX.115

- network.host: XXX.XXX.XXX.115


- cluster.name: bigdatagroup.com


- node.name: n2.bigdatagroup


- http.port: 9200


- bootstrap.memory_lock: false 


- bootstrap.system_call_filter: false


- discovery.zen.ping.unicast.hosts: ["XXX.XXX.XXX.161", "XXX.XXX.XXX.179"]


- ​

Host: XXX.XXX.XXX.179

- network.host: XXX.XXX.XXX.179


- cluster.name: bigdatagroup.com


- node.name: n3.bigdatagroup


- http.port: 9200


- bootstrap.memory_lock: false 


- bootstrap.system_call_filter: false


- discovery.zen.ping.unicast.hosts: ["XXX.XXX.XXX.161", "XXX.XXX.XXX.115"]

## Run es


create run_es
```
#!/bin/bash
export JAVA_HOME=/home/wangjie/jdk1.8.0_131
export PATH=JAVA_HOME/bin:PATH
ulimit -n 65536
/home/wangjie/elasticsearch-5.4.1/bin/elasticsearch -d
```

run run_es

```
chmod +x run_es
./run_es
ps aux|grep elastic
```



