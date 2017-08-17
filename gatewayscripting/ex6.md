## Exercise 6: Querystrings
The querystring module provides an easy way to deal with query strings.
The query string is an essential part when it comes to REST APIs.
While in the past we usually used the convert query params action to deal with query string, now we can natively work with those in GatewayScript.

To access the functions in the querystring module, use the require('querystring') statement.
The following methods are supported: escape(), parse(), stringify(), unescape()

## Note
The webIDE doesn't have the possibility to change the request URL.
Use a REST client or chrome developer tools in order to send a query string as part of your URL.

## The challenge
1) Output the querystring received in the request as a JSON object
2) Send the following JSON request
```
{
  "key1": "value1",
  "key2": ["value2a","value2b"],
  "key3": "value3"
}
```

And create a querystring out of it. Print the querystring to the console.
