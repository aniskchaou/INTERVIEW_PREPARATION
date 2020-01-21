## 190) What do you understand by an IO stream?

The stream is a sequence of data that flows from source to destination. It is composed of bytes. In Java, three streams are created for us automatically.

System.out: standard output stream
System.in: standard input stream
System.err: standard error stream

## 191) What is the difference between the Reader/Writer class hierarchy and the InputStream/OutputStream class hierarchy?

 - The Reader/Writer class hierarchy is character-oriented, and the
   InputStream/OutputStream class hierarchy is byte-oriented.
   
 - The ByteStream classes are used to perform input-output of 8-bit
   bytes whereas the CharacterStream classes are used to perform the
   input/output for the 16-bit Unicode system.

 

## 192) What are the super most classes for all the streams?

All the stream classes can be divided into two types of classes that are ByteStream classes and CharacterStream Classes. The ByteStream classes are further divided into InputStream classes and OutputStream classes. CharacterStream classes are also divided into Reader classes and Writer classes. 
**The SuperMost classes for all the InputStream classes is java.io.InputStream and for all the output stream classes is java.io.OutPutStream. Similarly, for all the reader classes, the super-most class is java.io.Reader, and for all the writer classes, it is java.io.Writer.**



## 198) In Java, How many ways you can take input from the console?

In Java, there are three ways by using which, we can take input from the console.

**Using BufferedReader class:** 

    import java.io.BufferedReader;   
    import java.io.IOException;   
    import java.io.InputStreamReader;   
    public class Person   
    {   
        public static void main(String[] args) throws IOException    
        {   
          System.out.println("Enter the name of the person");  
            BufferedReader reader = new BufferedReader(new InputStreamReader(System.in));   
            String name = reader.readLine();   
            System.out.println(name);           
        }   
    }   

**Using Scanner class:** 

    import java.util.*;    
    public class ScannerClassExample2 {      
          public static void main(String args[]){                         
              String str = "Hello/This is JavaTpoint/My name is Abhishek.";    
              //Create scanner with the specified String Object    
              Scanner scanner = new Scanner(str);    
              System.out.println("Boolean Result: "+scanner.hasNextBoolean());              
              //Change the delimiter of this scanner    
              scanner.useDelimiter("/");    
              //Printing the tokenized Strings    
              System.out.println("---Tokenizes String---");     
            while(scanner.hasNext()){    
                System.out.println(scanner.next());    
            }    
              //Display the new delimiter    
              System.out.println("Delimiter used: " +scanner.delimiter());              
              scanner.close();    
              }      
    } 

   
    
**Using Console class:** 

    import java.io.Console;    
    class ReadStringTest{      
    public static void main(String args[]){      
    Console c=System.console();      
    System.out.println("Enter your name: ");      
    String n=c.readLine();      
    System.out.println("Welcome "+n);      
    }      
    }    


