# Configure ES Plugin for 3 node

## Install Ingest attachment

Download ingest attachment : <https://artifacts.elastic.co/downloads/elasticsearch-plugins/ingest-attachment/ingest-attachment-5.4.1.zip>

```
export JAVA_HOME=/home/wangjie/jdk1.8.0_131
export PATH=JAVA_HOME/bin:PATH
./elasticsearch-plugin install file:///home/wangjie/downloads/ingest-attachment-5.4.1.zip

```

## Config

 elasticsearch.yml

```xml
## Add CORS Support
http.cors.enabled : true
http.cors.allow-origin : "*"
http.cors.allow-methods : OPTIONS, HEAD, GET, POST, PUT, DELETE
http.cors.allow-headers : X-Requested-With,X-Auth-Token,Content-Type,Content-Length,Authorization
http.max_content_length : 500mb
## Add ingest-attachment
plugin.mandatory: ingest-attachment

```



