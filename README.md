# elasticdump
<h2>Backup and Restore ElasticSearch in Kubernetes</h2>
 apply the backup and restore pod yamls.

<h2>Backup and Restore ElasticSearch using Command Line</h2>

- Dump  using source and destination elastisearch URLs:
The following command dumps the data from the myindex index from source elasticsearch and restores to the destination easticsearch:

     `$ elasticdump --input=http://old-elasticsearch:9200/myindex --output=http://new-elasticsearch:9200/myindex`


- Dump by storing in a file.
  1. Storing dump in a file: <br>
    `$ elasticdump --input=http://localhost:9200/myindex --output=myindex.json`

  2. Restoring from the file: <br>
   `$ elasticdump --input=myindex.json --output=http://localhost:9200/myindex`


We can view all the indexes using this command: <br>
`$ elasticdump --input=http://localhost:9200 --output=$ | grep "\"index\"" | sed 's/.*: \"//' | sed 's/\".*//'`


So, if we want to dump all the indexes, we can loop the dump and restore command for using elasticdump.
<br>
<br>



Reference: https://github.com/elasticsearch-dump/elasticsearch-dump

