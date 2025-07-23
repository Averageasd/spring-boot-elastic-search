# delete index
DELETE /customers

# create index with explicit mapping
# even tho a field in elastic search can accept null, array the type still has to match.
# ex: for a field of type integer, we cannot assign it an array of type string.
PUT /customers
{
  "mappings": {
    "properties": {
      "name": {
        "type": "text"
      },
      "score": {
        "type": "integer"
      }
    }
  }
}

# get mapping
GET /customers/_mapping

# bulk insert
POST /customers/_bulk
{ "create": {} } { "name": "sam", "score": 15 } { "create": {} } { "name": "mike", "score": null } { "create": {} } { "name": "jake", "score": [] } { "create": {} } { "name": "john", "score": [10, 15, 20] } { "create": {} } { "name": "nancy" }


# query all
GET /customers/_search