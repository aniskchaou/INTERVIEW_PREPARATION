## Singly linked list Examples in Java

-   Linked List can be defined as a collection of objects called nodes that are randomly stored in the memory.
-   A node contains two fields, i.e. data stored at that particular address and the pointer which contains the address of the next node in the memory.
-   The last node of the list contains the pointer to the null.
- 
1.  public  class LinkedListExamples
2.  {
3.  Node head; // head of list
4.  static  class Node {
5.  int data;
6.  Node next;
7.  Node(int d) { data = d; next=null; }
8.  }
9.  /* This function prints contents of the linked list starting from head */
10.  public  void display()
11.  {
12.  Node n = head;
13.  while (n != null)
14.  {
15.  System.out.print(n.data+" \n");
16.  n = n.next;
17.  }
18.  }
19.  /* method to create a simple linked list with 3 nodes*/
20.  public  static  void main(String[] args)
21.  {
22.  /* Start with the empty list. */
23.  LinkedListExamples list = new LinkedListExamples();

25.  list.head = new Node(100);
26.  Node second = new Node(200);
27.  Node third = new Node(300);

29.  list.head.next = second; // Link first node with the second node
30.  second.next = third; // Link first node with the second node
31.  list.display();
32.  }
33.  }
## create and display a singly linked list
1.  public  class SinglyLinkedList {
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

31.  //display() will display all the nodes present in the list
32.  public  void display() {
33.  //Node current will point to head
34.  Node current = head;

35.  if(head == null) {
36.  System.out.println("List is empty");
37.  return;
38.  }
39.  System.out.println("Nodes of singly linked list: ");
40.  while(current != null) {
41.  //Prints each node by incrementing pointer
42.  System.out.print(current.data + " ");
43.  current = current.next;
44.  }
45.  System.out.println();
46.  }

47.  public  static  void main(String[] args) {

48.  SinglyLinkedList sList = new SinglyLinkedList();

49.  //Add nodes to the list
50.  sList.addNode(1);
51.  sList.addNode(2);
52.  sList.addNode(3);
53.  sList.addNode(4);

54.  //Displays the nodes present in the list
55.  sList.display();
56.  }
57.  }

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
## create and display a singly linked list
1.  public  class SinglyLinkedList {

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

31.  //display() will display all the nodes present in the list
32.  public  void display() {
33.  //Node current will point to head
34.  Node current = head;

35.  if(head == null) {
36.  System.out.println("List is empty");
37.  return;
38.  }
39.  System.out.println("Nodes of singly linked list: ");
40.  while(current != null) {
41.  //Prints each node by incrementing pointer
42.  System.out.print(current.data + " ");
43.  current = current.next;
44.  }
45.  System.out.println();
46.  }

47.  public  static  void main(String[] args) {

48.  SinglyLinkedList sList = new SinglyLinkedList();

49.  //Add nodes to the list
50.  sList.addNode(1);
51.  sList.addNode(2);
52.  sList.addNode(3);
53.  sList.addNode(4);

54.  //Displays the nodes present in the list
55.  sList.display();
56.  }
57.  }
58. 
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
64. ## remove duplicate elements from a singly linked list
65.  public  class RemoveDuplicate {

66.  //Represent a node of the singly linked list
67.  class Node{
68.  int data;
69.  Node next;

70.  public Node(int data) {
71.  this.data = data;
72.  this.next = null;
73.  }
74.  }

75.  //Represent the head and tail of the singly linked list
76.  public Node head = null;
77.  public Node tail = null;

78.  //addNode() will add a new node to the list
79.  public  void addNode(int data) {
80.  //Create a new node
81.  Node newNode = new Node(data);

82.  //Checks if the list is empty
83.  if(head == null) {
84.  //If list is empty, both head and tail will point to new node
85.  head = newNode;
86.  tail = newNode;
87.  }
88.  else {
89.  //newNode will be added after tail such that tail's next will point to newNode
90.  tail.next = newNode;
91.  //newNode will become new tail of the list
92.  tail = newNode;
93.  }
94.  }

95.  //removeDuplicate() will remove duplicate nodes from the list
96.  public  void removeDuplicate() {
97.  //Node current will point to head
98.  Node current = head, index = null, temp = null;

99.  if(head == null) {
100.  return;
101.  }
102.  else {
103.  while(current != null){
104.  //Node temp will point to previous node to index.
105.  temp = current;
106.  //Index will point to node next to current
107.  index = current.next;

108.  while(index != null) {
109.  //If current node's data is equal to index node's data
110.  if(current.data == index.data) {
111.  //Here, index node is pointing to the node which is duplicate of current node
112.  //Skips the duplicate node by pointing to next node
113.  temp.next = index.next;
114.  }
115.  else {
116.  //Temp will point to previous node of index.
117.  temp = index;
118.  }
119.  index = index.next;
120.  }
121.  current = current.next;
122.  }
123.  }
124.  }

125.  //display() will display all the nodes present in the list
126.  public  void display() {
127.  //Node current will point to head
128.  Node current = head;
129.  if(head == null) {
130.  System.out.println("List is empty");
131.  return;
132.  }
133.  while(current != null) {
134.  //Prints each node by incrementing pointer
135.  System.out.print(current.data + " ");
136.  current = current.next;
137.  }
138.  System.out.println();
139.  }

140.  public  static  void main(String[] args) {

141.  RemoveDuplicate sList = new RemoveDuplicate();

142.  //Adds data to the list
143.  sList.addNode(1);
144.  sList.addNode(2);
145.  sList.addNode(3);
146.  sList.addNode(2);
147.  sList.addNode(2);
148.  sList.addNode(4);
149.  sList.addNode(1);

150.  System.out.println("Originals list: ");
151.  sList.display();

152.  //Removes duplicate nodes
153.  sList.removeDuplicate();

154.  System.out.println("List after removing duplicates: ");
155.  sList.display();
156.  }
157.  }
158. 
159.
## search an element in a singly linked list
1.  public  class SearchLinkedList {
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
31.  //searchNode() will search for a given node in the list
32.  public  void searchNode(int data) {
33.  Node current = head;
34.  int i = 1;
35.  boolean flag = false;
36.  //Checks whether list is empty
37.  if(head == null) {
38.  System.out.println("List is empty");
39.  }
40.  else {
41.  while(current != null) {
42.  //Compares node to be found with each node present in the list
43.  if(current.data == data) {
44.  flag = true;
45.  break;
46.  }
47.  i++;
48.  current = current.next;
49.  }
50.  }
51.  if(flag)
52.  System.out.println("Element is present in the list at the position : " + i);
53.  else
54.  System.out.println("Element is not present in the list");
55.  }

57.  public  static  void main(String[] args) {

59.  SearchLinkedList sList = new SearchLinkedList();

61.  //Add nodes to the list
62.  sList.addNode(1);
63.  sList.addNode(2);
64.  sList.addNode(3);
65.  sList.addNode(4);

67.  //Search for node 2 in the list
68.  sList.searchNode(2);
69.  //Search for a node in the list
70.  sList.searchNode(7);
71.  }}