# SERIALIZATION IN JAVA:

## INTRO:
#### What is serialization?
  to serialize an object means to convert its state to a byte (byte=8bits) stream so that the byte stream can be reverted back into a copy of the object.

#### Why serialization?
- object storage: to read/write objects to/from file/database/disk <br>
- object transmission via network: to read/write objects to/from network

#### Alternative for java serialization:
- json: if consumer is a browser using ajax/jquery (ie, web services) <br>
- xml <br>
  Note: java serialization is used: if consumer is another Java program (eg: RMI)

## BASICS - MUST KNOW:
#### How to serialize/deserialize?
  serialize: 
  ```
  new ObjectOutputStream(new FileOutputStream("fileName.txt/.ser/no extension")).writeObject(object);
  ```
  deserialize: 
```
  objectName = (className) new ObjectInputStream(new FileInputStream("fileName.txt/.ser/no extension")).readObject();
```
  (NOTE: use try/catch)

#### What if object contains ref var?
  Just put 'implements serializable' for every nested class, then automatic serialization & deserialization happens

#### What if referred object's source code isn't available(ie,you can't put 'implements Serializable on that referred object')?
   - Use 'transient': avoids serialization of that referred object.  <br>
  
   - If no transient given: runtime exception: NonSerializableException at while serializing ie, at writeObject().  <br>
  
   - If transient given:  <br>
            - and if tried to access the transient variable after deserialization -> returns 'null' <br>
  		      - and if tried to access the transient variable's state after deserialization -> returns 'NullPointerException''  <br>
            
  Note: transient can also be used for primitives.
  

#### What if referred object's state has to be serialized?
   - Put transient (else NonSerializableException will be thrown).  <br>
  
   - Implement writeObject(): defaultWriteObject() + writeInt(collar.getSize())  <br>
  
   - Implement readObject(): defaultReadObject() + new ReferredClass(readInt())  <br>


## BASICS - NEXT:
#### Inheritance and Serialization:
a) when only superclass implements Serializable: subclasses automatically serialized  <br>

b) when only subclass implements Serializable: while deserialzing, subclass states get serialized values, but inherited states get constructed values or initial values given during declaration

#### Collection/Array and Serialization:
 - If you serialize a collection or an array, every element must be
serializable! A single non-serializable element will cause serialization to fail.  <br>

 - Also, collection interfaces (List) are not serializable, the concrete collection classes 
in the Java API are (ArrayList).

#### Static and Serialization: 
Static variables are not serialized/deserialized

#### Versioning problem: 
Serializing and deserializing should be in the same version

## EXTRAS:
#### Rules:
Don't forget try-catch and .close() while serializing and de-serializing

#### Marker interface: 
Marker interface means interface with no methods. eg: Serializable

#### Why isn't class Object serializable? 
There are some things in Java that simply cannot
be serialized because they are runtime specific. Things like streams, threads, runtime,
etc. and even some GUI classes (which are connected to the underlying OS) cannot
be serialized. What is and is not serializable in the Java API is NOT part of the exam,
but you'll need to keep them in mind if you're serializing complex objects.
