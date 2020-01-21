

## 200) How can you make a class serializable in Java?

A class can become serializable by implementing the Serializable interface.


## 202) Can a Serialized object be transferred via network?

Yes

## 203) What is Deserialization?

Deserialization is the process of reconstructing the object from the serialized state. 

    import java.io.*;  
    class Depersist{  
     public static void main(String args[])throws Exception{  
        
      ObjectInputStream in=new ObjectInputStream(new FileInputStream("f.txt"));  
      Student s=(Student)in.readObject();  
      System.out.println(s.id+" "+s.name);  
      
      in.close();  
     }  
    }  

211 ravi

## 204) What is the transient keyword?

If you define any data member as transient, it will not be serialized. By determining transient keyword, the value of variable need not persist when it is restored. More details.



.