# SERIALIZATION IN JAVA:

0. ## INTRO:
#### what is serialization?
  to serialize an object means to convert its state to a byte (byte=8bits) stream so that the byte stream can be reverted back into a copy of the object.

#### why serialization?
  storage: to read/write objects to/from file/database/disk
  network transmission: to read/write objects to/from network

#### alternative for java serialization:
  json: if consumer is a browser using ajax/jquery
  xml
  Note: java serialization is used: if consumer is another Java program (eg: RMI)

1. ## BASICS:
#### how to serialize/deserialize?
  serialize: new ObjectOutputStream(new FileOutputStream("fileName.txt/.ser/no extension")).writeObject(object)
  deserialize: objectName = (className) new ObjectInputStream(new FileInputStream("fileName.txt/.ser/no extension")).readObject()
  (NOTE: use try/catch)

#### what if object contains ref var?
  automatic ser/deser
  just put 'implements serializable for every class'

#### what if referred object's source code isn't available(ie,you can't put 'implements Serializable on that referred object')?
  transient: avoids serialization of that referred object
  (if no transient given: runtime exception: NonSerializableException at while serializing ie, at writeObject())
  (if transient given: - and if tried to access the transient variable after deserialization -> returns 'null'
  		      - and if tried to access the transient variable's state after deserialization -> returns 'NullPointerException'')
  Note: transient can also be used for primitives.
  

#### what if referred object's state has to be serialized?
  put transient (else NonSerializableException will be thrown)
  implement writeObject(): defaultWriteObject() + writeInt(collar.getSize())
  implement readObject(): defaultReadObject() + new Collar(readInt())

2. ## Inheritance and Serialization:
a) when only superclass implements Serializable: subclasses automatically serialized
b) when only subclass implements Serializable: while deserialzing, subclass states get serialized values, but inherited states get constructed values or initial values given during declaration

3. ## Collection/Array and Serialization:
If you serialize a collection or an array, every element must be
serializable! A single non-serializable element will cause serialization to fail.
Also, collection interfaces (List) are not serializable, the concrete collection classes 
in the Java API are (ArrayList).

4. ## Static and Serialization: 
Static variables not serialized/deserialized

5. ## Versioning problem: 
serializing and deserializing should be in the same version

6. ## Note:
#### Rules:
Don't forget try-catch and .close() while serializing and de-serializing

#### Marker interface: 
interface with no methods. eg: Serializable

#### Why isn't class Object serializable? 
There are some things in Java that simply cannot
be serialized because they are runtime specific. Things like streams, threads, runtime,
etc. and even some GUI classes (which are connected to the underlying OS) cannot
be serialized. What is and is not serializable in the Java API is NOT part of the exam,
but you'll need to keep them in mind if you're serializing complex objects.
