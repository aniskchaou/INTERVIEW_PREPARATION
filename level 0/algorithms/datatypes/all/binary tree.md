
## program to search a node in a Binary Tree

    public class SearchBinaryTree {
    
    //Represent a node of binary tree
        public static class Node {
    
            int data;
    
            Node left;
    
            Node right;
    
            public Node(int data) {
    
    //Assign data to the new node, set left and right children to null
                this.data = data;
    
                this.left = null;
    
                this.right = null;
    
            }
    
        }
    
    //Represent the root of binary tree
        public Node root;
    
        public static boolean flag = false;
    
        public SearchBinaryTree() {
    
            root = null;
    
        }
    
    //searchNode() will search for the particular node in the binary tree
        public void searchNode(Node temp, int value) {
    
    //Check whether tree is empty
            if (root == null) {
    
                System.out.println("Tree is empty");
    
            } else {
    
    //If value is found in the given binary tree then, set the flag to true
                if (temp.data == value) {
    
                    flag = true;
    
                    return;
    
                }
    
    //Search in left subtree
                if (flag == false && temp.left != null) {
    
                    searchNode(temp.left, value);
    
                }
    
    //Search in right subtree
                if (flag == false && temp.right != null) {
    
                    searchNode(temp.right, value);
    
                }
    
            }
    
        }
    
        public static void main(String[] args) {
    
            SearchBinaryTree bt = new SearchBinaryTree();
    
    //Add nodes to the binary tree
            bt.root = new Node(1);
    
            bt.root.left = new Node(2);
    
            bt.root.right = new Node(3);
    
            bt.root.left.left = new Node(4);
    
            bt.root.right.left = new Node(5);
    
            bt.root.right.right = new Node(6);
    
    //Search for node 5 in the binary tree
            bt.searchNode(bt.root, 5);
    
            if (flag) {
                System.out.println("Element is present in the binary tree");
            } else {
                System.out.println("Element is not present in the binary tree");
            }
    
        }
    
    }

## find the sum of all the nodes of a binary tree

    public class SumOfNodes {
    
        //Represent the node of binary tree
        public static class Node {
    
            int data;
            Node left;
            Node right;
    
            public Node(int data) {
                //Assign data to the new node, set left and right children to null
                this.data = data;
                this.left = null;
                this.right = null;
            }
        }
    
        //Represent the root of binary tree
        public Node root;
    
        public SumOfNodes() {
            root = null;
        }
    
        //calculateSum() will calculate the sum of all the nodes present in the binary tree
        public int calculateSum(Node temp) {
            int sum, sumLeft, sumRight;
            sum = sumRight = sumLeft = 0;
    
            //Check whether tree is empty
            if (root == null) {
                System.out.println("Tree is empty");
                return 0;
            } else {
                //Calculate the sum of nodes present in left subtree
                if (temp.left != null) {
                    sumLeft = calculateSum(temp.left);
                }
    
                //Calculate the sum of nodes present in right subtree
                if (temp.right != null) {
                    sumRight = calculateSum(temp.right);
                }
    
                //Calculate the sum of all nodes by adding sumLeft, sumRight and root node's data
                sum = temp.data + sumLeft + sumRight;
                return sum;
            }
        }
    
          public static void main(String[] args) {
    
            SumOfNodes bt = new SumOfNodes();
            //Add nodes to the binary tree
            bt.root = new Node(5);
            bt.root.left = new Node(2);
            bt.root.right = new Node(9);
            bt.root.left.left = new Node(1);
            bt.root.right.left = new Node(8);
            bt.root.right.right = new Node(6);
    
            //Display the sum of all the nodes in the given binary tree
            System.out.println("Sum of all nodes of binary tree: " + bt.calculateSum(bt.root));
        }
    }
## Display Nodes

    public class Testalgo {
        Node head;
        
        static class Node{
            int data;
        Node next;
        Node previous;
    
            public Node(int data) {
                this.data = data;
                this.next = null;
                this.previous = null;
            }
        
        
        }
        
        static void display(Node head)
        {
            if(head==null)
            {
                return ;
            }else
            {
                System.err.println(""+head.data);
                
                if(head.previous!=null)
                    display(head.previous);
                
                if (head.next!=null) 
                    display(head.next);
            }
        }
        
        public static void main(String[] args) {
          Testalgo t=new Testalgo();
          t.head=new Node(1);
          t.head.previous=new Node(6);
          t.head.next=new Node(7);
          t.head.next.next=new Node(8);
          t.head.next.previous=new Node(9);
          
            display(t.head);
        }
    
     
    }
