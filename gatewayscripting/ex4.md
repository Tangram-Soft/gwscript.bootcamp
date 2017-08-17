## Exercise 4: Manipulating message headers
Tempering with a message isn't just about tempering with the payload but also with its headers.
Using the headers module we can access the message headers.

Header APIs are exported in header-metadata.js. To access the header metadata, you must have a require statement; such the following statement.
var hm = require('header-metadata');

The headers module is broken down into three submodules: original, current, and response.
1) original - Represents the original collection of headers received off the wire. Original headers are read-only. For a request rule, these headers are the ones in the request from the client. For a response rule, these headers are the ones in the response from the remote, target host.
2) current - Represents the current state of the headers as they are passed from action to action in a processing rule. The processing rule can be a request rule or a response rule. Current headers are read/write.
3) response - Represents the collection of headers that is used for a response that is accessed in the request rule. The response header is used for a loopback firewall or when skip-backside is used in a Multi-Protocol Gateway. Response headers are read/write.

You can use the get(), set() and remove() methods to access the headers.
For example:

hm.original.get('content-type')

Will return the value of the content-type header

hm.response.set('content-type','text/xml')

Will set the the value of content-type header to 'text/xml'.

## Note

Remember that the WebIDE is a loopback service :)

## The challenge
Add a new header to your request:  
testHeader: compl

Write a gwscript that reads the headers and add "ete" to its value.
