Python ElasticSearch API

http://elasticsearch-py.readthedocs.io/en/master/index.html



```python
cluster  = ['9.110.74.161:9200','9.110.74.115:9200','9.110.74.179:9200']
es = Elasticsearch(cluster,timeout=300)
index_name = 'gov_file_index'
type_name='my_type'
pipeline_name='attachment'

doc={
  'file_name': os.path.basename(fPath),
  'data': file_code,
}
res = es.index(index=index_name, 
               doc_type=type_name, 
               id=i, 
               pipeline=pipeline_name, 
               body=doc, 
               #refresh ='true'
              )
```

