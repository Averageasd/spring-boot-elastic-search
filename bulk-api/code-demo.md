PUT /my-index


### delete index
DELETE /my-index

### create an index
PUT /my-index

### bulk insert
POST /my-index/_bulk
{"create": {}} { "name": "king" } { "create": {} } { "name": "item1" } { "create": {} } { "name": "item2" } { "create": {} } { "name": "item3" }

### bulk insert with file
use this command to post file to elastic search for bulk insert:
curl -XPOST "http://localhost:9200/my-index/_bulk" -H "Content-Type: application/x-ndjson" --data-binary @data.ndjson