//split when it encouters any non-numerical characters
//for example, in this example, we split this string that contains whitespaces into words. 
POST /_analyze
{
  "text": "This is a sample text to see how tokens are generated.",
  "tokenizer": "standard"
}

//in this case, we will get b as characters that we can put into our inverted index.
POST /_analyze
{
  "text": "Reach out to <b>Support</b> at support@domain.com or send mail to 123,Non Main Street, Atlanta, for assistance!",
  "tokenizer": "standard"
}

// in this case, we want to strop out html special characters and then split at spaces and other non-alphanumerical chars
// we won't have b's anymore
POST /_analyze
{
  "text": "Reach out to <b>Support</b> at support@domain.com or send mail to 123,Non Main Street, Atlanta, for assistance!",
  "char_filter": [
    "html_strip"
  ],
  "tokenizer": "standard"
}

// we dont want to split at @, basically preserving emails
POST /_analyze
{
  "text": "Reach out to Support at support@domain.com or send mail to 123,Non Main Street, Atlanta, for assistance!",
  "tokenizer": "uax_url_email"
}

// keyword - noop
// we don't want to do any splitting. 
POST /_analyze
{
  "text": "Reach out to Support at support@domain.com or send mail to 123,Non Main Street, Atlanta, for assistance!",
 "tokenizer": "keyword"
}