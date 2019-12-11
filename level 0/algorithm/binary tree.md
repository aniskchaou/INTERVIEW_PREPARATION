
## program to search a node in a Binary Tree
1.  public  class SearchBinaryTree {

2.  //Represent a node of binary tree
3.  public  static  class Node{
4.  int data;
5.  Node left;
6.  Node right;

7.  public Node(int data){
8.  //Assign data to the new node, set left and right children to null
9.  this.data = data;
10.  this.left = null;
11.  this.right = null;
12.  }
13.  }

14.  //Represent the root of binary tree
15.  public Node root;

16.  public  static  boolean flag = false;

17.  public SearchBinaryTree(){
18.  root = null;
19.  }

20.  //searchNode() will search for the particular node in the binary tree
21.  public  void searchNode(Node temp, int value){
22.  //Check whether tree is empty
23.  if(root == null){
24.  System.out.println("Tree is empty");
25.  }
26.  else{
27.  //If value is found in the given binary tree then, set the flag to true
28.  if(temp.data == value){
29.  flag = true;
30.  return;
31.  }
32.  //Search in left subtree
33.  if(flag == false && temp.left != null){
34.  searchNode(temp.left, value);
35.  }
36.  //Search in right subtree
37.  if(flag == false && temp.right != null){
38.  searchNode(temp.right, value);
39.  }
40.  }
41.  }

42.  public  static  void main(String[] args) {

43.  SearchBinaryTree bt = new SearchBinaryTree();
44.  //Add nodes to the binary tree
45.  bt.root = new Node(1);
46.  bt.root.left = new Node(2);
47.  bt.root.right = new Node(3);
48.  bt.root.left.left = new Node(4);
49.  bt.root.right.left = new Node(5);
50.  bt.root.right.right = new Node(6);

51.  //Search for node 5 in the binary tree
52.  bt.searchNode(bt.root, 5);

53.  if(flag)
54.  System.out.println("Element is present in the binary tree");
55.  else
56.  System.out.println("Element is not present in the binary tree");
57.  }
58.  }
59. 
60. ## find the sum of all the nodes of a binary tree
1.  public  class SumOfNodes {

3.  //Represent the node of binary tree
4.  public  static  class Node{
5.  int data;
6.  Node left;
7.  Node right;

9.  public Node(int data){
10.  //Assign data to the new node, set left and right children to null
11.  this.data = data;
12.  this.left = null;
13.  this.right = null;
14.  }
15.  }

17.  //Represent the root of binary tree
18.  public Node root;

20.  public SumOfNodes(){
21.  root = null;
22.  }

24.  //calculateSum() will calculate the sum of all the nodes present in the binary tree
25.  public  int calculateSum(Node temp){
26.  int sum, sumLeft, sumRight;
27.  sum = sumRight = sumLeft = 0;

29.  //Check whether tree is empty
30.  if(root == null) {
31.  System.out.println("Tree is empty");
32.  return  0;
33.  }
34.  else {
35.  //Calculate the sum of nodes present in left subtree
36.  if(temp.left != null)
37.  sumLeft = calculateSum(temp.left);

39.  //Calculate the sum of nodes present in right subtree
40.  if(temp.right != null)
41.  sumRight = calculateSum(temp.right);

43.  //Calculate the sum of all nodes by adding sumLeft, sumRight and root node's data
44.  sum = temp.data + sumLeft + sumRight;
45.  return sum;
46.  }
47.  }

49.  public  static  void main(String[] args) {

51.  SumOfNodes bt = new SumOfNodes();
52.  //Add nodes to the binary tree
53.  bt.root = new Node(5);
54.  bt.root.left = new Node(2);
55.  bt.root.right = new Node(9);
56.  bt.root.left.left = new Node(1);
57.  bt.root.right.left = new Node(8);
58.  bt.root.right.right = new Node(6);

60.  //Display the sum of all the nodes in the given binary tree
61.  System.out.println("Sum of all nodes of binary tree: " + bt.calculateSum(bt.root));
62.  }
63.  }
