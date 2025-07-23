DELETE /customers

# explicitly tells ElasticSearch to map fields to types
# email would not be tokenized and elastic search would not be able to locate email.
# to change this, change type of email to text. 
PUT /customers
{
  "mappings": {
    "properties": {
      "name": {
        "type": "text"
      },
      "age": {
        "type": "integer"
      },
      "email": {
        "type": "keyword"
      }
    }
  }
}

# email would not be tokenized and elastic search would not be able to locate email.
# to change this, change type of email to text. 
PUT /customers
{
  "mappings": {
    "properties": {
      "name": {
        "type": "text"
      },
      "age": {
        "type": "integer"
      },
      "email": {
        "type": "text"
      }
    }
  }
}

GET /customers/_mapping

POST /customers/_bulk
{ "create": {} } { "name": "John Doe", "age": 15, "email": "john@doe.com" } { "create": {} } { "name": "Jane Smith", "age": 25, "email": "jane@smith.com" } { "create": {} } { "name": "Alice Brown", "age": 30, "email": "alice@brown.com" }

GET /customers/_search?q=brown
GET /customers/_search?q=brown.com
GET /customers/_search
