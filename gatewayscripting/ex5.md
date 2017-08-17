## Exercise 5: Access the service variables
Service variables are an essential part of a traveling transaction.
Access this module with a ```require('service-metadata')``` statement.

You can use the getVar(), setVar() and list() methods to do actions against service variables.

## Note
You can write variables in dotted or slash notation.
Dotted notation
```
var sm = require('service-metadata');
sm.mpgw.skipBackside = true;
```
Slash, or URL, notation
```
var sm = require('service-metadata');
sm.setVar('var://service/mpgw/skip-backside', true) ;
```

## The challenge
Output the transaction-id of the current transaction.
