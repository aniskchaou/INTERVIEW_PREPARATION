## **What is meant by `Serialization`?**

Ans: Converting a file into a byte stream is known as Serialization. The objects in the file is converted to the bytes for security purposes.  **For this, we need to implement java.io.Serializable interface.**  It has no method to define.

## **Which methods are used during `Serialization` and `Deserialization` process?**

Ans: ObjectOutputStream and ObjectInputStream classes are higher level java.io. package.

`ObjectOutputStream.writeObject`  —->Serialize the object and write the serialized object to a file.

`ObjectInputStream.readObject`  —> Reads the file and deserializes the object.

**To be serialized, an object must implement the serializable interface.**

## **Difference between `Serialization` and `Deserialization` in Java.**

Serialization is the process which  **is used to convert the objects into byte stream**

Deserialization  **is the opposite process of serialization where we can get the objects back from the byte stream**.

## **What is `SerialVersionUID`?**

  Ans: Whenever an object is Serialized, the object is stamped with a version ID number for the object class. This ID is called the SerialVersionUID.

## **In java, how we can `disallow serialization` of variables?**

we can use the keyword  `transient`  while declaring them.

```
public class transientExample  { 
private transient trans_var; 
 }

```
