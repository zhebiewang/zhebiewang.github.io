# Highlight in ES

[Highlight](https://www.elastic.co/guide/en/elasticsearch/reference/current/search-request-highlighting.html)

http://localhost:5601/app/kibana#



```
GET /gc_index/slides/_search
{
    "query" : {
        "match": { "content": "basalt" }
    },
    "highlight" : {
        "fields" : {
            "content" : {"type" : "plain",
            "fragment_size" : 10}
        }
    }
}
```

```json
"highlight": {
          "content": [
            """
:) Dickenson Fault
(Gp:) Campbell Fault
(Gp:) 13 L Campbell
(Gp:) 13 L Red Lake
(Gp:) <em>Ultramafic</em>
(Gp
""",
"""
:) <em>Ultramafic</em>
(Gp:) Campbell Diorite
(Gp:) Lamp Dyke
(Gp:) Altered  Dyke
	Cross Section of 12_07_NC and 21_11_F  
"""
          ]
  }
```



Unified highlighter

Plain highlighter

Fast vector highlighter