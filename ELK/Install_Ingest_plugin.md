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

Pipeline

```json
PUT _ingest/pipeline/attachment
{
  "description" : "Extract attachment information",
  "processors" : [
    {
      "attachment" : {
        "field" : "data",
        "indexed_chars" : -1
      }
    }
  ]
}
```

Index

```json
PUT gov_file_index
{ 
    "mappings" : { 
        "my_type" : { 
            "properties" : { 
                "attachment.data" : { 
                    "type": "text", 
                    "analyzer" : "standard" 
                } 
            } 
        } 
    } 
}
```



## Case

```json
PUT gov_file_index/my_type/1?pipeline=attachment&refresh=true&pretty=1
{
    "id": "1",
    "filename": "1.txt",
    "data" : "e1xydGYxXGFuc2kNCkxvcmVtIGlwc3VtIGRvbG9yIHNpdCBhbWV0DQpccGFyIH0="
}
```



