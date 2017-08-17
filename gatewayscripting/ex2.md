## Exercise 2: The session.output context
We usually would want to use GatewayScript to temper with the message.
The session.output context returns the context that is specified by the Output property of the GatewayScript action.

We can change the context using write().

## Note
write() method in general supports writing to any contexts and not only the output context.

## The challenge:  
Write the following JSON object to your output context:
{
  "message" : "success"
}
