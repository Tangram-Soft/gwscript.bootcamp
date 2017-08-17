## Exercise 3: Reading a document from a context

As explained an exercise 2, we are usually temper with the message that flows through our GatewayScript.
So reading the input is important as well!
In order to read a specific document from a context, we use the ReadAs...() functions.
We have 4 different ReadAs functions:
1) ReadAsBuffer
2) ReadAsBuffers
3) ReadAsJSON
4) ReadAsXML

In all of our exercises today we will be working with JSON payloads.

The syntax for the ReadAs functions is:
session.context.readAsJSON (errorObject, jsonObject){
  ...
})

context - Is the name of the data that is used in a processing action. The context can be INPUT, input, or a named context.

errorObject - Contains the error message text and a description of the error, suggestions, and a stack trace. If the input context is empty, the message text in the error object is Null context.

jsonObject - The JSON document. It contains a JSON representation of the context body, if no error occurs.


## Note
You are probably asking yourself what the difference between buffer and buffers.
When contexts are small, use the readAsBuffer() function. Use the readAsBuffers() function when a context is large. The readAsBuffer() function requires a contiguous memory allocation. The readAsBuffer() function is faster but is more demanding on the memory system. The readAsBuffers() function does not require contiguous memory to populate the Buffers object.

## The challenge

Place the following message in your request body:
{
  "message" : "Hi from GatewayScript!"
}

And output the following message:
{
  "echo" : {
    "message" : "Hi from GatewayScript!"
  }
}
