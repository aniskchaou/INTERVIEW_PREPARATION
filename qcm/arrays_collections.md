

## **Difference between Array and Array List.**

**Size**  should be given at the time of array declaration.

String[] name = new String[2] name[1] = “book”  **//with index**

**Size**  may not be required. It changes the  `size dynamically`.

ArrayList name = new ArrayList name.add(“book”)  **//no index**




## Collections

 - **Iterator --> Collections**
 - **Collections --> List, Queue, Dequeue, Set, SortedSet**


 - List --> ArrayList, Vector, LinkedList
 - Queue --> PriorityQueue
 - Set -->HashSet, LinkedHashSet*

## List

List interface is the child interface of Collection interface. It inhibits a list type data structure in which 

 - we can store **the ordered collection** of objects.
 - It **can have duplicate values**.

 

## ArrayList

 - store the duplicate element of different data types.
 - maintains the insertion order
 - is non-synchronized.

 The elements stored in the ArrayList class can be randomly accessed.
```
ArrayList<String> list=new ArrayList<String>();
list.add("Ravi");  
list.add("Vijay");  
list.add("Ravi");  
list.add("Ajay");  
 
Iterator itr=list.iterator();  
while(itr.hasNext()){  
System.out.println(itr.next());  
}  

```

## Vector

Vector uses a dynamic array to store the data elements. It is similar to ArrayList.  

 - It is synchronized
 - contains many methods that are not the part of Collection framework.

## LinkedList


 - It can store the duplicate elements.
 - It maintains the insertion order and is not synchronized.

  In LinkedList, the manipulation is fast because no shifting is required.

```
LinkedList ll = new LinkedList();
      
      // add elements to the linked list
      ll.add("F");
      ll.add("B");
      ll.add("D");
      ll.add("E");
      ll.add("C");
      ll.addLast("Z");
      ll.addFirst("A");
      ll.add(1, "A2");

```

## Stack

 - The stack is the subclass of Vector.
 - It implements the last-in-first-out data structure, i.e.,

```
Stack<String> stack = new Stack<String>();  
stack.push("Ayush");  
stack.push("Garvit");  
stack.push("Amit");  
stack.push("Ashish");  
stack.push("Garima");  
stack.pop();  
Iterator<String> itr=stack.iterator();  
while(itr.hasNext()){  
System.out.println(itr.next());  
}  

```

## Queue

 **Queue --> PriorityQueue**

 **PriorityQueue**

The PriorityQueue class implements the Queue interface.  **It holds the elements or objects which are to be processed by their priorities.**  PriorityQueue doesn't allow null values to be stored in the queue.

```
PriorityQueue<String> queue=new PriorityQueue<String>();  
queue.add("Amit Sharma");  
queue.add("Vijay Raj");  
queue.add("JaiShankar");  
queue.add("Raj");  
System.out.println("head:"+queue.element());  
System.out.println("head:"+queue.peek());  
System.out.println("iterating the queue elements:");  
Iterator itr=queue.iterator();  
while(itr.hasNext()){  
System.out.println(itr.next());  
}  
queue.remove();  
queue.poll();  
System.out.println("after removing two elements:");  
Iterator<String> itr2=queue.iterator();  

while(itr2.hasNext()){  
System.out.println(itr2.next());  
}  

```

## Set

**Set --> LinkedHashSet, HashSet**  Set Interface in Java is present in java.util package. It extends the Collection interface.  _**It represents the unordered set of elements which doesn't allow us to store the duplicate items.**_  We can store at most one null value in Set. Set is implemented by HashSet, LinkedHashSet, and TreeSet.

## HashSet

HashSet class implements Set Interface. It represents the collection that uses a hash table for storage.

 - Hashing is used to store the elements in the HashSet.
 - It contains unique items.

```
HashSet<String> set=new HashSet<String>();  
set.add("Ravi");  
set.add("Vijay");  
set.add("Ravi");  
set.add("Ajay");  
//Traversing elements  
Iterator<String> itr=set.iterator();  
while(itr.hasNext()){  
System.out.println(itr.next());  
}  

```

**SortedSet --> TreeSet**

## TreeSet

Java TreeSet class implements the Set interface that uses a tree for storage.  **Like HashSet, TreeSet also contains unique elements.**  

 - the access and retrieval time of TreeSet is quite fast.
 - The elements in TreeSet stored in ascending order.

## Map

**Map --> HashMap, LinkedHashMap, TreeMap**  

 - A map contains values on the basis of key, i.e. key and value pair.
 - Each key and value pair is known as an entry.
 - A Map contains unique keys.



 - **HashMap**  HashMap is the implementation of Map,  **but it doesn't maintain any order.*
 
 - **LinkedHashMap**  LinkedHashMap is the implementation of Map. It inherits HashMap class.  **It maintains insertion order.**

 

 - **TreeMap**  TreeMap is the implementation of Map and SortedMap.  **It maintains ascending order.**

```
Map<Integer,String> map=new HashMap<Integer,String>();  
  map.put(100,"Amit");  
  map.put(101,"Vijay");  
  map.put(102,"Rahul");  
  //Elements can traverse in any order  
  for(Map.Entry m:map.entrySet()){  
   System.out.println(m.getKey()+" "+m.getValue());  
  }  

```

## collections methods

 - **public boolean add(E e)**

It is used to insert an element in this collection.

 - **public boolean addAll(Collection<? extends E> c)**

It is used to insert the specified collection elements in the invoking collection.

 - **public boolean remove(Object element)**

It is used to delete an element from the collection.

 - **public boolean removeAll(Collection<?> c)**

It is used to delete all the elements of the specified collection from the invoking collection.

 - **public int size()**

It returns the total number of elements in the collection.

 - **public void clear()**

It removes the total number of elements from the collection.

 - **public boolean contains(Object element)**

It is used to search an element.

 - **public Iterator iterator()**

It returns an iterator.

 - **public Object[] toArray()**

It converts collection into array.

 - **public boolean isEmpty()**

It checks if collection is empty.

 - **public boolean equals(Object element)**

It matches two collections.



## Arrays methods

 - **public static int binarySearch(Object[] a, Object key)**

Searches the specified array of Object ( Byte, Int , double, etc.) for the specified value using the binary search algorithm. 

 - **public static boolean equals(long[] a, long[] a2)**

Returns true if the two specified arrays of longs are equal to one another. 


**public static void fill(int[] a, int val)**

Assigns the specified int value to each element of the specified array of ints. The same method could be used by all other primitive data types (Byte, short, Int, etc.)

**public static void sort(Object[] a)**

Sorts the specified array of objects into an ascending order, according to the natural ordering of its elements.
