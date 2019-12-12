
## Singly linked list Examples in Java

-   Linked List can be defined as a collection of objects called nodes that are randomly stored in the memory.
-   A node contains two fields, i.e. data stored at that particular address and the pointer which contains the address of the next node in the memory.
-   The last node of the list contains the pointer to the null.
- 

    public class LinkedListExamples {
    
        Node head; // head of list
    
        static class Node {
    
            int data;
    
            Node next;
    
            Node(int d) {
                data = d;
                next = null;
            }
    
        }
    
        /* This function prints contents of the linked list starting from head */
        public void display() {
    
            Node n = head;
    
            while (n != null) {
    
                System.out.print(n.data + " \n");
    
                n = n.next;
    
            }
    
        }
    
        /* method to create a simple linked list with 3 nodes*/
        public static void main(String[] args) {
    
            /* Start with the empty list. */
            LinkedListExamples list = new LinkedListExamples();
    
            list.head = new Node(100);
    
            Node second = new Node(200);
    
            Node third = new Node(300);
    
            list.head.next = second; // Link first node with the second node
    
            second.next = third; // Link first node with the second node
    
            list.display();
    
        }
    
    }





## search an element in a singly linked list

    public class SearchLinkedList {
    
    //Represent a node of the singly linked list
    
    class Node{
    
    int data;
    
    Node next;
    
    public Node(int data) {
    
    this.data = data;
    
    this.next = null;
    
    }
    
    }
    
    //Represent the head and tail of the singly linked list
    
    public Node head = null;
    
    public Node tail = null;
    
    //addNode() will add a new node to the list
    
    public void addNode(int data) {
    
    //Create a new node
    
    Node newNode = new Node(data);
    
    //Checks if the list is empty
    
    if(head == null) {
    
    //If list is empty, both head and tail will point to new node
    
    head = newNode;
    
    tail = newNode;
    
    }
    
    else {
    
    //newNode will be added after tail such that tail’s next will point to newNode
    
    tail.next = newNode;
    
    //newNode will become new tail of the list
    
    tail = newNode;
    
    }
    
    }
    
    //searchNode() will search for a given node in the list
    
    public void searchNode(int data) {
    
    Node current = head;
    
    int i = 1;
    
    boolean flag = false;
    
    //Checks whether list is empty
    
    if(head == null) {
    
    System.out.println("List is empty");
    
    }
    
    else {
    
    while(current != null) {
    
    //Compares node to be found with each node present in the list
    
    if(current.data == data) {
    
    flag = true;
    
    break;
    
    }
    
    i++;
    
    current = current.next;
    
    }
    
    }
    
    if(flag)
    
    System.out.println("Element is present in the list at the position : " + i);
    
    else
    
    System.out.println("Element is not present in the list");
    
    }
    
    public static void main(String[] args) {
    
    SearchLinkedList sList = new SearchLinkedList();
    
    //Add nodes to the list
    
    sList.addNode(1);
    
    sList.addNode(2);
    
    sList.addNode(3);
    
    sList.addNode(4);
    
    //Search for node 2 in the list
    
    sList.searchNode(2);
    
    //Search for a node in the list
    
    sList.searchNode(7);
    
    }}
## create a singly linked list of n nodes and count the number of nodes
1.  public  class CountNodes {

2.  //Represent a node of singly linked list
3.  class Node{
4.  int data;
5.  Node next;

6.  public Node(int data) {
7.  this.data = data;
8.  this.next = null;
9.  }
10.  }

11.  //Represent the head and tail of the singly linked list
12.  public Node head = null;
13.  public Node tail = null;

14.  //addNode() will add a new node to the list
15.  public  void addNode(int data) {
16.  //Create a new node
17.  Node newNode = new Node(data);

18.  //Checks if the list is empty
19.  if(head == null) {
20.  //If list is empty, both head and tail will point to new node
21.  head = newNode;
22.  tail = newNode;
23.  }
24.  else {
25.  //newNode will be added after tail such that tail's next will point to newNode
26.  tail.next = newNode;
27.  //newNode will become new tail of the list
28.  tail = newNode;
29.  }
30.  }

31.  //countNodes() will count the nodes present in the list
32.  public  int countNodes() {
33.  int count = 0;
34.  //Node current will point to head
35.  Node current = head;

36.  while(current != null) {
37.  //Increment the count by 1 for each node
38.  count++;
39.  current = current.next;
40.  }
41.  return count;
42.  }

43.  //display() will display all the nodes present in the list
44.  public  void display() {
45.  //Node current will point to head
46.  Node current = head;
47.  if(head == null) {
48.  System.out.println("List is empty");
49.  return;
50.  }
51.  System.out.println("Nodes of singly linked list: ");
52.  while(current != null) {
53.  //Prints each node by incrementing pointer
54.  System.out.print(current.data + " ");
55.  current = current.next;
56.  }
57.  System.out.println();
58.  }

59.  public  static  void main(String[] args) {

60.  CountNodes sList = new CountNodes();

61.  //Add nodes to the list
62.  sList.addNode(1);
63.  sList.addNode(2);
64.  sList.addNode(3);
65.  sList.addNode(4);

66.  //Displays the nodes present in the list
67.  sList.display();

68.  //Counts the nodes present in the given list
69.  System.out.println("Count of nodes present in the list: " + sList.countNodes());
70.  }
71.  }
72. 


## delete a node from the beginning of the singly linked list
1.  public  class DeleteStart {

2.  //Represent a node of the singly linked list
3.  class Node{
4.  int data;
5.  Node next;

6.  public Node(int data) {
7.  this.data = data;
8.  this.next = null;
9.  }
10.  }

11.  //Represent the head and tail of the singly linked list
12.  public Node head = null;
13.  public Node tail = null;

14.  //addNode() will add a new node to the list
15.  public  void addNode(int data) {
16.  //Create a new node
17.  Node newNode = new Node(data);

18.  //Checks if the list is empty
19.  if(head == null) {
20.  //If list is empty, both head and tail will point to new node
21.  head = newNode;
22.  tail = newNode;
23.  }
24.  else {
25.  //newNode will be added after tail such that tail's next will point to newNode
26.  tail.next = newNode;
27.  //newNode will become new tail of the list
28.  tail = newNode;
29.  }
30.  }

31.  //deleteFromStart() will delete a node from the beginning of the list
32.  public  void deleteFromStart() {

33.  //Checks if the list is empty
34.  if(head == null) {
35.  System.out.println("List is empty");
36.  return;
37.  }
38.  else {
39.  //Checks whether the list contains only one node
40.  //If not, the head will point to next node in the list and tail will point to the new head.
41.  if(head != tail) {
42.  head = head.next;
43.  }
44.  //If the list contains only one node
45.  //then, it will remove it and both head and tail will point to null
46.  else {
47.  head = tail = null;
48.  }
49.  }
50.  }

51.  //display() will display all the nodes present in the list
52.  public  void display() {
53.  //Node current will point to head
54.  Node current = head;
55.  if(head == null) {
56.  System.out.println("List is empty");
57.  return;
58.  }
59.  while(current != null) {
60.  //Prints each node by incrementing pointer
61.  System.out.print(current.data + " ");
62.  current = current.next;
63.  }
64.  System.out.println();
65.  }

66.  public  static  void main(String[] args) {

67.  DeleteStart sList = new DeleteStart();

68.  //Adds data to the list
69.  sList.addNode(1);
70.  sList.addNode(2);
71.  sList.addNode(3);
72.  sList.addNode(4);

73.  //Printing original list
74.  System.out.println("Original List: ");
75.  sList.display();

76.  while(sList.head != null) {
77.  sList.deleteFromStart();
78.  //Printing updated list
79.  System.out.println("Updated List: ");
80.  sList.display();
81.  }
82.  }
83.  }
84. 
## create a singly linked list of n nodes and display it in reverse order
1.  public  class ReverseList {
2.  //Represent a node of the singly linked list
3.  class Node{
4.  int data;
5.  Node next;

6.  public Node(int data) {
7.  this.data = data;
8.  this.next = null;
9.  }
10.  }

11.  //Represent the head and tail of the singly linked list
12.  public Node head = null;
13.  public Node tail = null;

14.  //addNode() will add a new node to the list
15.  public  void addNode(int data) {
16.  //Create a new node
17.  Node newNode = new Node(data);

18.  //Checks if the list is empty
19.  if(head == null) {
20.  //If list is empty, both head and tail will point to new node
21.  head = newNode;
22.  tail = newNode;
23.  }
24.  else {
25.  //newNode will be added after tail such that tail's next will point to newNode
26.  tail.next = newNode;
27.  //newNode will become new tail of the list
28.  tail = newNode;
29.  }
30.  }

31.  //reverse() will help the reverse the order of the list
32.  public  void reverse(Node current) {
33.  //Checks if list is empty
34.  if(head == null) {
35.  System.out.println("List is empty");
36.  return;
37.  }
38.  else {
39.  //Checks if the next node is null, if yes then prints it.
40.  if(current.next == null) {
41.  System.out.print(current.data + " ");
42.  return;
43.  }
44.  //Recursively calls the reverse function
45.  reverse(current.next);
46.  System.out.print(current.data + " ");
47.  }
48.  }

49.  //display() will display all the nodes present in the list
50.  public  void display() {
51.  //Node current will point to head
52.  Node current = head;

53.  if(head == null) {
54.  System.out.println("List is empty");
55.  return;
56.  }

57.  while(current != null) {
58.  //Prints each node by incrementing pointer
59.  System.out.print(current.data + " ");
60.  current = current.next;
61.  }
62.  System.out.println();
63.  }

64.  public  static  void main(String[] args) {

65.  ReverseList sList = new ReverseList();

66.  //Add nodes to the list
67.  sList.addNode(1);
68.  sList.addNode(2);
69.  sList.addNode(3);
70.  sList.addNode(4);

71.  System.out.println("Original List: ");
72.  sList.display();

73.  System.out.println("Reversed List: ");
74.  //Print reversed list
75.  sList.reverse(sList.head);
76.  }
77.  }
78. 
## insert a new node at the beginning of the singly linked list
1.  public  class InsertStart {

2.  //Represent a node of the singly linked list
3.  class Node{
4.  int data;
5.  Node next;

6.  public Node(int data) {
7.  this.data = data;
8.  this.next = null;
9.  }
10.  }

11.  //Represent the head and tail of the singly linked list
12.  public Node head = null;
13.  public Node tail = null;

14.  //addAtStart() will add a new node to the beginning of the list
15.  public  void addAtStart(int data) {
16.  //Create a new node
17.  Node newNode = new Node(data);

18.  //Checks if the list is empty
19.  if(head == null) {
20.  //If list is empty, both head and tail will point to new node
21.  head = newNode;
22.  tail = newNode;
23.  }
24.  else {
25.  //Node temp will point to head
26.  Node temp = head;
27.  //newNode will become new head of the list
28.  head = newNode;
29.  //Node temp(previous head) will be added after new head
30.  head.next = temp;
31.  }
32.  }

33.  //display() will display all the nodes present in the list
34.  public  void display() {
35.  //Node current will point to head
36.  Node current = head;
37.  if(head == null) {
38.  System.out.println("List is empty");
39.  return;
40.  }
41.  System.out.println("Adding nodes to the start of the list: ");
42.  while(current != null) {
43.  //Prints each node by incrementing pointer
44.  System.out.print(current.data + " ");
45.  current = current.next;
46.  }
47.  System.out.println();
48.  }

49.  public  static  void main(String[] args) {

50.  InsertStart sList = new InsertStart();

51.  //Adding 1 to the list
52.  sList.addAtStart(1);
53.  sList.display();

54.  //Adding 2 to the list
55.  sList.addAtStart(2);
56.  sList.display();

57.  //Adding 3 to the list
58.  sList.addAtStart(3);
59.  sList.display();

60.  //Adding 4 to the list
61.  sList.addAtStart(4);
62.  sList.display();
63.  }
64.  }
65. 
## insert a new node at the end of the singly linked list
1.  public  class InsertEnd {

2.  //Represent a node of the singly linked list
3.  class Node{
4.  int data;
5.  Node next;

6.  public Node(int data) {
7.  this.data = data;
8.  this.next = null;
9.  }
10.  }

11.  //Represent the head and tail of the singly linked list
12.  public Node head = null;
13.  public Node tail = null;

14.  //addAtEnd() will add a new node to the end of the list
15.  public  void addAtEnd(int data) {
16.  //Create a new node
17.  Node newNode = new Node(data);

18.  //Checks if the list is empty
19.  if(head == null) {
20.  //If list is empty, both head and tail will point to new node
21.  head = newNode;
22.  tail = newNode;
23.  }
24.  else {
25.  //newNode will be added after tail such that tail's next will point to newNode
26.  tail.next = newNode;
27.  //newNode will become new tail of the list
28.  tail = newNode;
29.  }
30.  }

31.  //display() will display all the nodes present in the list
32.  public  void display() {
33.  //Node current will point to head
34.  Node current = head;
35.  if(head == null) {
36.  System.out.println("List is empty");
37.  return;
38.  }
39.  System.out.println("Adding nodes to the end of the list: ");
40.  while(current != null) {
41.  //Prints each node by incrementing pointer
42.  System.out.print(current.data + " ");
43.  current = current.next;
44.  }
45.  System.out.println();
46.  }

47.  public  static  void main(String[] args) {

48.  InsertEnd sList = new InsertEnd();

49.  //Adding 1 to the list
50.  sList.addAtEnd(1);
51.  sList.display();

52.  //Adding 2 to the list
53.  sList.addAtEnd(2);
54.  sList.display();

55.  //Adding 3 to the list
56.  sList.addAtEnd(3);
57.  sList.display();

58.  //Adding 4 to the list
59.  sList.addAtEnd(4);
60.  sList.display();
61.  }
62.  }
63.  
## remove duplicate elements from a singly linked list

    public class RemoveDuplicate {
    
    //Represent a node of the singly linked list
        class Node {
    
            int data;
    
            Node next;
    
            public Node(int data) {
    
                this.data = data;
    
                this.next = null;
    
            }
    
        }
    
    //Represent the head and tail of the singly linked list
        public Node head = null;
    
        public Node tail = null;
    
    //addNode() will add a new node to the list
        public void addNode(int data) {
    
    //Create a new node
            Node newNode = new Node(data);
    
    //Checks if the list is empty
            if (head == null) {
    
    //If list is empty, both head and tail will point to new node
                head = newNode;
    
                tail = newNode;
    
            } else {
    
    //newNode will be added after tail such that tail’s next will point to newNode
                tail.next = newNode;
    
    //newNode will become new tail of the list
                tail = newNode;
    
            }
    
        }
    
    //removeDuplicate() will remove duplicate nodes from the list
        public void removeDuplicate() {
    
    //Node current will point to head
            Node current = head, index = null, temp = null;
    
            if (head == null) {
    
                return;
    
            } else {
    
                while (current != null) {
    
    //Node temp will point to previous node to index.
                    temp = current;
    
    //Index will point to node next to current
                    index = current.next;
    
                    while (index != null) {
    
    //If current node’s data is equal to index node’s data
                        if (current.data == index.data) {
    
    //Here, index node is pointing to the node which is duplicate of current node
    //Skips the duplicate node by pointing to next node
                            temp.next = index.next;
    
                        } else {
    
    //Temp will point to previous node of index.
                            temp = index;
    
                        }
    
                        index = index.next;
    
                    }
    
                    current = current.next;
    
                }
    
            }
    
        }
    
    //display() will display all the nodes present in the list
        public void display() {
    
    //Node current will point to head
            Node current = head;
    
            if (head == null) {
    
                System.out.println("List is empty");
    
    return;
    
            }
    
            while (current != null) {
    
    //Prints each node by incrementing pointer
                System.out.print(current.data + " ");
    
                current = current.next;
    
            }
    
            System.out.println();
    
        }
    
        public static void main(String[] args) {
    
            RemoveDuplicate sList = new RemoveDuplicate();
    
    //Adds data to the list
            sList.addNode(1);
    
            sList.addNode(2);
    
            sList.addNode(3);
    
            sList.addNode(2);
    
            sList.addNode(2);
    
            sList.addNode(4);
    
            sList.addNode(1);
    
            System.out.println("Originals list: ");
    
            sList.display();
    
    //Removes duplicate nodes
            sList.removeDuplicate();
    
            System.out.println("List after removing duplicates: ");
    
            sList.display();
    
        }
    
    }