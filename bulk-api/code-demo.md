PUT /my-index


# delete index
DELETE /my-index

# create an index
PUT /my-index

POST /my-index/_bulk
{"create": {}} { "name": "king" } { "create": {} } { "name": "item1" } { "create": {} } { "name": "item2" } { "create": {} } { "name": "item3" }
