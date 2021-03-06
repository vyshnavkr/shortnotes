# STRING, STRINGBUILDER, STRINGBUFFER

## String:
 - #### Immutable: 
 	Any modifications on an object will create a new object. <br/>
 	'A modified string object is abandoned upon creation' if its NOT ASSIGNED TO ANY REFERENCE VARIABLE.
 - #### Final: 
 	String class is marked final so that nobody can override the behaviors of any of the String methods. Thus protecting immutability.
 - #### Memory:
```
	String s = "abc";			// creates one String object in String Constant Pool (SCP is inside Heap) <br/>
	String s = new String("abc"); 		// creates one String object in normal (nonpool) memory of Heap and s will refer to it, and IF NO 'abc' IS PREVIOUSLY CREATED IN SCP, then one String object is created in SCP too.
```
 - #### Methods: 
```
	charAt(), concat(), equalsIgnoreCase(), toLowerCase(), toUpperCase(), length(), replace(), substring(), toString(), trim()
```

## StringBuilder, StringBuffer:
 - #### Why:
 	For MUTABLE strings (pg 476). <br/>
   	Thus, no need to assign back after modification
 - #### StringBuilder vs StringBuffer:
 	StringBuilder: faster <br/>
   	StringBuffer: thread-safe
 - #### Methods: 
```
	append() (similar to concat() of String), insert(), delete(), reverse(), toString()
```
