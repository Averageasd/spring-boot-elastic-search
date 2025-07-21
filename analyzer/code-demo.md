// strip html tags
// we will no longer see <b><b>
POST /_analyze
{
  "text": "I work with tools like <b>Text-Analyzer</b> everyday to process large datasets!!",
  "char_filter": [
    "html_strip"
  ]
}

POST /_analyze
{
  "text": "I work with tools like <b>Text-Analyzer</b> daily to process large datasets!!",
  "char_filter": [
    {
      "type": "mapping",
      "mappings": [
        "daily => everyday",
        "- => _",
        "!! => ."
      ]
    },
    "html_strip"
  ]
}

// use to do transformation at character level using regex
// this means: find any matching substrings in group 1 (\\d+) that are preceded by $ and replacing them numbers without $ followed by dollars
// ex: $5 -> 5 dollars. 

POST /_analyze
{
  "text": "At $100, the product is quite expensive.",
  "char_filter": [
    {
      "type": "pattern_replace",
      "pattern": "\\$(\\d+)",
      "replacement": "$1 dollars"
    }
  ]
}