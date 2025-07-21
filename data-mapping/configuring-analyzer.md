# delete index
DELETE /blogs

# create index with explicit mapping
PUT /blogs
{
 "mappings": {
   "properties": {
       "title": {
         "type": "text"
       },
       "body": {
         "type": "text"
       }
   }
 }
}

GET /blogs/_search?q=em

# get mapping
GET /blogs/_mapping