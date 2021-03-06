## request body structure

Message Type Id : **03**

request body is always empty

## response body structure

Message Type Id : **83**

* [dsa key values pairs format](../common/DSA-Binary-Encoding.md#key-value-pairs-encoding)

  * attributes: 
     * key starts with @
     * value is any msgpack encoded data (with size limitation)
  * configs : 
     * key starts with $
     * value is any msgpack encoded data (with size limitation)
  * children
     * key starts with other character
     * value is msgpack format of basic map node structure, including $is, $writable, $invokable information

### base path header

Base path is an optional header for a list response, when broker pass a list response from responder to requester, it should append the responder's node path to the base path, so the requester will be able to tell where is the root node of that responder


### special configs

* $is : the profile node position
* $invokable : indicate whether the node is an action node that can be invoked, the value is the minimal permission level requester needs to invoke this action.
* $type : indicate the [Value Type](Value-Types) of the current node. when this config exists, that means the current node has a value that requester can subscribe.


* pamameters : the parameter structure of a action node



