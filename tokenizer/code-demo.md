# standard - divides text into terms on word boundaries & it removes most punctuation symbols. 
# unicode text segmentation algorithm - https://unicode.org/reports/tr29/#Word_Boundaries
# mostly splits when it encouters any non-alphanumeric char (with some exceptions)
POST /_analyze
{
  "text": "This is a sample text to see how tokens are generated.",
  "tokenizer": "standard"
}