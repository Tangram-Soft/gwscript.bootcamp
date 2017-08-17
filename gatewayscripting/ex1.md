## Exercise 1: Printing messages to the console
DataPower's log is probably one of the best way to troubleshoot your services. Using the console module you can write log messages.

Use console.log() to write your desired message to the log.

## Note
You can write a log message at different log levels.

console.emerg("emergency");
console.alert("alert");
console.critical("critical");
console.error("error");
console.warn("warn");
console.notice("notice");
//Both of the following methods log at "info" level
console.info("info") ;
console.log("log");
//Both of the following methods log at "debug" level
console.debug("debug");
console.trace("trace");


## The challenge:  
Go to the WebIDE, and write a line that prints "Hello World" to the log using console.log().
save your code and execute it.
You can see the result on the lower right pane.
Choose the "Log" tab to see the transaction log.

Can you see it? :)
