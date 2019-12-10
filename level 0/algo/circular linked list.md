## create a circular linked list of n nodes and count the number of nodes.
1.  public  class CountNodes {
2.  //Represents the node of list.
3.  public  class Node{
4.  int data;
5.  Node next;
6.  public Node(int data) {
7.  this.data = data;
8.  }
9.  }

10.  public  int count;
11.  //Declaring head and tail pointer as null.
12.  public Node head = null;
13.  public Node tail = null;

14.  //This function will add the new node at the end of the list.
15.  public  void add(int data){
16.  //Create new node
17.  Node newNode = new Node(data);
18.  //Checks if the list is empty.
19.  if(head == null) {
20.  //If list is empty, both head and tail would point to new node.
21.  head = newNode;
22.  tail = newNode;
23.  newNode.next = head;
24.  }
25.  else {
26.  //tail will point to new node.
27.  tail.next = newNode;
28.  //New node will become new tail.
29.  tail = newNode;
30.  //Since, it is circular linked list tail will point to head.
31.  tail.next = head;
32.  }
33.  }

34.  //This function will count the nodes of circular linked list
35.  public  void countNodes() {
36.  Node current = head;
37.  do{
38.  //Increment the count variable by 1 for each node
39.  count++;
40.  current = current.next;
41.  }while(current != head);
42.  System.out.println("Count of nodes present in circular linked list: "+count);
43.  }

44.  public  static  void main(String[] args) {
45.  CountNodes cl = new CountNodes();
46.  cl.add(1);
47.  cl.add(2);
48.  cl.add(4);
49.  cl.add(1);
50.  cl.add(2);
51.  cl.add(3);
52.  //Counts the number of nodes present in the list
53.  cl.countNodes();
54.  }
55.  }
## create and display a circular linked list
1.  public  class BinaryTreeToDLL {
2.  //Represent a node of the binary tree
3.  public  static  class Node{
4.  int data;
5.  Node left;
6.  Node right;

7.  public Node(int data) {
8.  this.data = data;
9.  this.left = null;
10.  this.right = null;
11.  }
12.  }

13.  //Represent the root of the binary tree

14.  public Node root;

15.  //Represent the head and tail of the doubly linked list
16.  Node head, tail = null;

17.  //convertbtToDLL() will convert the given binary tree to corresponding doubly linked list
18.  public  void convertbtToDLL(Node node) {
19.  //Checks whether node is null
20.  if(node == null)
21.  return;

22.  //Convert left subtree to doubly linked list
23.  convertbtToDLL(node.left);

24.  //If list is empty, add node as head of the list
25.  if(head == null) {
26.  //Both head and tail will point to node
27.  head = tail = node;
28.  }
29.  //Otherwise, add node to the end of the list
30.  else {
31.  //node will be added after tail such that tail's right will point to node
32.  tail.right = node;
33.  //node's left will point to tail
34.  node.left = tail;
35.  //node will become new tail
36.  tail = node;
37.  }

38.  //Convert right subtree to doubly linked list
39.  convertbtToDLL(node.right);
40.  }

41.  //display() will print out the nodes of the list
42.  public  void display() {
43.  //Node current will point to head
44.  Node current = head;
45.  if(head == null) {
46.  System.out.println("List is empty");
47.  return;
48.  }
49.  System.out.println("Nodes of generated doubly linked list: ");
50.  while(current != null) {
51.  //Prints each node by incrementing the pointer.

52.  System.out.print(current.data + " ");
53.  current = current.right;
54.  }
55.  System.out.println();
56.  }

57.  public  static  void main(String[] args) {

58.  BinaryTreeToDLL bt = new BinaryTreeToDLL();
59.  //Add nodes to the binary tree
60.  bt.root = new Node(1);
61.  bt.root.left = new Node(2);
62.  bt.root.right = new Node(3);
63.  bt.root.left.left = new Node(4);
64.  bt.root.left.right = new Node(5);
65.  bt.root.right.left = new Node(6);
66.  bt.root.right.right = new Node(7);

67.  //Converts the given binary tree to doubly linked list
68.  bt.convertbtToDLL(bt.root);

69.  //Displays the nodes present in the list
70.  bt.display();
71.  }
72.  }
## find the maximum and minimum value node from a circular linked list
1.  public  class MinMax {
2.  //Represents the node of list.
3.  public  class Node{
4.  int data;
5.  Node next;
6.  public Node(int data) {
7.  this.data = data;
8.  }
9.  }

11.  //Declaring head and tail pointer as null.
12.  public Node head = null;
13.  public Node tail = null;

15.  //This function will add the new node at the end of the list.
16.  public  void add(int data){
17.  //Create new node
18.  Node newNode = new Node(data);
19.  //Checks if the list is empty.
20.  if(head == null) {
21.  //If list is empty, both head and tail would point to new node.
22.  head = newNode;
23.  tail = newNode;
24.  newNode.next = head;
25.  }
26.  else {
27.  //tail will point to new node.
28.  tail.next = newNode;
29.  //New node will become new tail.
30.  tail = newNode;
31.  //Since, it is circular linked list tail will points to head.
32.  tail.next = head;
33.  }
34.  }

36.  //Finds out the minimum value node in the list
37.  public  void minNode() {
38.  Node current = head;
39.  //Initializing min to initial node data
40.  int min = head.data;
41.  if(head == null) {
42.  System.out.println("List is empty");
43.  }
44.  else {
45.  do{
46.  //If current node's data is smaller than min
47.  //Then replace value of min with current node's data
48.  if(min > current.data) {
49.  min = current.data;
50.  }
51.  current= current.next;
52.  }while(current != head);

54.  System.out.println("Minimum value node in the list: "+ min);
55.  }
56.  }

58.  //Finds out the maximum value node in the list
59.  public  void maxNode() {
60.  Node current = head;
61.  //Initializing max to initial node data
62.  int max = head.data;
63.  if(head == null) {
64.  System.out.println("List is empty");
65.  }
66.  else {
67.  do{
68.  //If current node's data is greater than max
69.  //Then replace value of max with current node's data
70.  if(max < current.data) {
71.  max = current.data;
72.  }
73.  current= current.next;
74.  }while(current != head);

76.  System.out.println("Maximum value node in the list: "+ max);
77.  }
78.  }

80.  public  static  void main(String[] args) {
81.  MinMax cl = new MinMax();
82.  //Adds data to the list
83.  cl.add(5);
84.  cl.add(20);
85.  cl.add(10);
86.  cl.add(1);
87.  //Prints the minimum value node in the list
88.  cl.minNode();
89.  //Prints the maximum value node in the list
90.  cl.maxNode();
91.  }
92.  }