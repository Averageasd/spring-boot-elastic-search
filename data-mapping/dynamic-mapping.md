DELETE /my-index

# this is implicit mapping. it will assume the types of the fields
POST /my-index/_doc
{
    "quantity": 10,
    "isAvailable": true,
    "lastUpdated": "2000/01/01"
}

# this one still works. 
POST /my-index/_doc
{
    "path": "02/02/2000"
}

GET /my-index/_mapping