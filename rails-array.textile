---
---
Our frontend is built with the Ruby on Rails application framework, which make it easy to build a scalable interface to ferry your notifications off to the correct location.

h3. Using an Array in a Request
Some of our API methods are required to be in the format of an array. Ruby on Rails includes an interesting and innovative way to handle this in request variables that you write to interface with our API. The format for specifying data in an array is shown below:

* {{message[]=hello}}
* {{message[]=there}}
* {{message[]=people}}

Or, in a constructed request string: {{message[]=hello&message[]=there&message[]=people}}

In this example, "message" is an array.

h3. Getting Help
As always, if you need help with this, join us in our [IRC support channel|IRC] and we'll answer any question you could ever have about our API. :)

