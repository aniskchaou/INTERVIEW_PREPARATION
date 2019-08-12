## search binary tree
    
        public class SearchBinaryTree {  
          
              //Represent a node of binary tree  
              public static class Node{  
                int data;  
                Node left;  
                Node right;  
          
                public Node(int data){  
                  //Assign data to the new node, set left and right children to null  
                  this.data = data;  
                  this.left = null;  
                  this.right = null;  
                }  
              }  
          
              //Represent the root of binary tree  
              public Node root;  
          
              public static boolean flag = false;  
          
              public SearchBinaryTree(){  
                root = null;  
              }  
          
              //searchNode() will search for the particular node in the binary tree  
              public void searchNode(Node temp, int value){  
                //Check whether tree is empty  
                if(root == null){  
                  System.out.println("Tree is empty");  
                }  
                else{  
                  //If value is found in the given binary tree then, set the flag to true  
                  if(temp.data == value){  
                    flag = true;  
                       return;  
                  }  
                  //Search in left subtree  
                  if(flag == false && temp.left != null){  
                     searchNode(temp.left, value);  
                  }  
                  //Search in right subtree  
                  if(flag == false && temp.right != null){  
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
          
                if(flag)  
                  System.out.println("Element is present in the binary tree");  
                else  
                  System.out.println("Element is not present in the binary tree");  
              }  
            }  

## Find Simple Closed Path for a given set of points



## Detect loop in a linked list

**Given a linked list, check if the linked list has loop or not.** 

    public class LinkedList { 
      
        static Node head; // head of list 
      
        /* Linked list Node*/
        static class Node { 
            int data; 
            Node next; 
            Node(int d) 
            { 
                data = d; 
                next = null; 
            } 
        } 
      
        /* Inserts a new Node at front of the list. */
        static public void push(int new_data) 
        { 
            /* 1 & 2: Allocate the Node & 
                      Put in the data*/
            Node new_node = new Node(new_data); 
      
            /* 3. Make next of new Node as head */
            new_node.next = head; 
      
            /* 4. Move the head to point to new Node */
            head = new_node; 
        } 
      
        // Returns true if there is a loop in linked 
        // list else returns false. 
        static boolean detectLoop(Node h) 
        { 
            HashSet<Node> s = new HashSet<Node>(); 
            while (h != null) { 
                // If we have already has this node 
                // in hashmap it means their is a cycle 
                // (Because you we encountering the 
                // node second time). 
                if (s.contains(h)) 
                    return true; 
      
                // If we are seeing the node for 
                // the first time, insert it in hash 
                s.add(h); 
      
                h = h.next; 
            } 
      
            return false; 
        } 
      
        /* Driver program to test above function */
        public static void main(String[] args) 
        { 
            LinkedList llist = new LinkedList(); 
      
            llist.push(20); 
            llist.push(4); 
            llist.push(15); 
            llist.push(10); 
      
            /*Create loop for testing */
            llist.head.next.next.next.next = llist.head; 
      
            if (detectLoop(head)) 
                System.out.println("Loop found"); 
            else
                System.out.println("No Loop"); 
        } 
    } 
      
### Java program to check if linked list is circular or not.

    /*
     * Java class to represent linked list data structure.
     */
    public class LinkedList {
        private Node head;
        public LinkedList() { this.head = new Node("head"); }   
        public Node head() { return head;}
       
        public void appendIntoTail(Node node) {
            Node current = head;
           
            //find last element of LinkedList i.e. tail
            while(current.next() != null){
                current = current.next();
            }
            //appending new node to tail in LinkedList
            current.setNext(node);
        }
       
        /*
         * If singly LinkedList contains Cycle then following would be true
         * 1) slow and fast will point to same node i.e. they meet
         * On the other hand if fast will point to null or next node of
         * fast will point to null then LinkedList does not contains cycle.
         */
        public boolean isCyclic(){
            Node fast = head;
            Node slow = head;
           
            while(fast!= _null_ && fast.next != null){
                fast = fast.next.next;
                slow = slow.next;
               
                //if fast and slow pointers are meeting then LinkedList is cyclic
                if(fast == slow ){
                    return true;
                }
            }
            return false;
        }
       
        @Override
        public String toString(){
            StringBuilder sb = new StringBuilder();
            Node current = head.next();
            while(current != null){
               sb.append(current).append("-->");
               current = current.next();
            }
            sb.delete(sb.length() - 3, sb.length()); // to remove --> from last node
           return sb.toString();
        }
    
        public static class Node {
            private Node next;
            private String data;
    
            public Node(String data) {
                this.data = data;
            }
    
            public String data() { return data; }
            public void setData(String data) { this.data = data;}
    
            public Node next() { return next; }
            public void setNext(Node next) { this.next = next; }
    
            @Override
            public String toString() {
                return this.data;
            }
        }
    }
## Heading Print path from root to a given node in a binary tree

    Input :          1
                   /   \
                  2     3
                 / \   /  \
                4   5  6   7
    
                   x = 5
    
    Output : 1->2->5


// Java implementation to print the path from root  
// to a given node in a binary tree  

    import java.util.ArrayList; 
    public class PrintPath { 
      
        // Returns true if there is a path from root  
        // to the given node. It also populates   
        // 'arr' with the given path  
        public static boolean hasPath(Node root, ArrayList<Integer> arr, int x)  
        {  
            // if root is NULL  
            // there is no path  
            if (root==null)  
                return false;  
            
            // push the node's value in 'arr'  
            arr.add(root.data);      
            
            // if it is the required node  
            // return true  
            if (root.data == x)      
                return true;  
            
            // else check whether the required node lies  
            // in the left subtree or right subtree of   
            // the current node  
            if (hasPath(root.left, arr, x) ||  
                hasPath(root.right, arr, x))  
                return true;  
            
            // required node does not lie either in the   
            // left or right subtree of the current node  
            // Thus, remove current node's value from   
            // 'arr'and then return false      
            arr.remove(arr.size()-1);  
            return false;              
        }  
      
        // function to print the path from root to the  
        // given node if the node lies in the binary tree  
        public static void printPath(Node root, int x)  
        {  
            // ArrayList to store the path  
            ArrayList<Integer> arr=new ArrayList<>(); 
          
            // if required node 'x' is present  
            // then print the path  
            if (hasPath(root, arr, x))  
            {  
                for (int i=0; i<arr.size()-1; i++)      
                    System.out.print(arr.get(i)+"->"); 
                System.out.print(arr.get(arr.size() - 1));     
            }  
            
            // 'x' is not present in the binary tree   
            else
                System.out.print("No Path");  
        }  
      
        public static void main(String args[]) { 
            Node root=new Node(1); 
            root.left = new Node(2);  
            root.right = new Node(3);  
            root.left.left = new Node(4);  
            root.left.right = new Node(5);  
            root.right.left = new Node(6);  
            root.right.right = new Node(7);  
            int x=5; 
            printPath(root, x); 
        } 
    } 
      
    // A node of binary tree  
    class Node  
    {  
        int data;  
        Node left, right;  
        Node(int data) 
        { 
            this.data=data; 
            left=right=null; 
        } 
    };  
    //This code is contributed by Gaurav Tiwari 

## Complete Floyd Cycle Detector

All the above code can be gathered together into a simple **Floyd Cycle Detector**:


