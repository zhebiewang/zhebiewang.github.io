- **Mongo DB info**
  - String ip = "9.115.81.163";
  - String ip='9.115.85.124';
  - int port = 27017; 
  - String dbName = "SparkTest";
  - String collName = "NbGjjInfo"; 


- **Config MongoDB**


- Run replicate set :   
  -  mongod --replSet myDevReplSet


- start new command line:  
  - mongo
  - rs.initiate()


- **Install mono-connector**


- pip install mongo-connector[elastic5]


- **Run**
  - mongo-connector -m 9.115.85.124:27017 -t 9.110.74.161:9200 -d elastic2_doc_manager
  - mongo-connector -m 127.0.0.1:27017 -t 9.110.74.161:9200 -d elastic2_doc_manager