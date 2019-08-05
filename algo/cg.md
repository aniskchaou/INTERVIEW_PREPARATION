# Move all zeroes
Given an array of random numbers, Push all the zero’s of a given array to the end of the array.  For example, if the given arrays is {1, 9, 8, 4, 0, 0, 2, 7, 0, 6, 0}, it should be changed to {1, 9, 8, 4, 2, 7, 6, 0, 0, 0, 0}. The order of all other elements should be same. Expected time complexity is O(n) and extra space is O(1).

**Example:**

    Input :  arr[] = {1, 2, 0, 4, 3, 0, 5, 0};
    Output : arr[] = {1, 2, 4, 3, 5, 0, 0};
    
    Input : arr[]  = {1, 2, 0, 0, 0, 3, 6};
    Output : arr[] = {1, 2, 3, 6, 0, 0, 0};

algo

       class PushZero 
        { 
           
            static void pushZerosToEnd(int arr[], int n) 
            { 
                int count = 0;  
    
                for (int i = 0; i < n; i++) 
                    if (arr[i] != 0) 
                        arr[count++] = arr[i]; 
    
                while (count < n) 
                    arr[count++] = 0; 
            } 
          
            /*Driver function to check for above functions*/
            public static void main (String[] args) 
            { 
                int arr[] = {1, 9, 8, 4, 0, 0, 2, 7, 0, 6, 0, 9}; 
                int n = arr.length; 
                pushZerosToEnd(arr, n); 
    
            } 
        } 

## reshape string

    public class Reshape_string {
    
        public static void main(String[] args) {
    
            Scanner input = new Scanner(System.in);
    
            String str;
    
            int num;
    
            //insert a string and a number
            System.out.print("Insert a string: ");
    
            str = input.nextLine();
    
            System.out.print("Insert the number of character: ");
    
            num = input.nextInt();
    
            //print the result of the reshape method
            System.out.println("Result of reshape method: " + '\n' + reshape(num, str));
    
        }
    
        public static String reshape(int n, String str) {
    
            //replace each space with empty string
            str = str.replace(" ", "");
    
            //insert a '\n' character each n characters
            String res = "";
    
            for (int i = 0; i < str.length(); i++) {
    
                if (i % n == 0 && i != 0) {
                    res = res + '\n' + str.charAt(i);
                } else {
                    res += str.charAt(i);
                }
    
            }
    
            return res;
    
        }
    
    }

## approximation pi

    import java.util.Scanner;
    
    import java.text.DecimalFormat;
    

    * 1 - 1/3 + 1/5 - 1/7 + 1/9 - ... = π/4
    
    
    public class Pi {
    
    public static void main(String[] args) {
    
    int n = getInput();
    
    double piValue = calculatePi(n);
    
    printResult(piValue);
    
    }
    
    private static double calculatePi(double n) {
    
    double pi = 0;
    
    for (int i = 1; i < n; i++) {
    
    pi += Math.pow(-1,i+1) / (2*i - 1);
    
    }
    
    return 4 * pi;
    
    }
    
    private static int getInput() {
    
    int n = 0;
    
    Scanner input = new Scanner(System.in);
    
    System.out.println("How many calculations should be run for the approximation?");
    
    try {
    
    n = Integer.parseInt(input.nextLine());
    
    } /** Handle input greater than Java's MAX_INT. **/
    
    catch (NumberFormatException e) {
    
    System.out.println("n is too large. Setting n to be the largest possible int value.");
    
    n = Integer.MAX_VALUE;
    
    }
    
    input.close();
    
    return n;
    
    }
    
    private static double calculateError(double piValue) {
    
    return Math.abs(1 - piValue / Math.PI) * 100;
    
    }
    
    private static void printResult(double piValue) {
    
    DecimalFormat df = new DecimalFormat("#.##");
    
    System.out.println("The value of pi is approximately " + piValue + ".");
    
    System.out.println("The calculated value is off by approximately " + df.format(calculateError(piValue)) + "%.");
    
    }
    
    }
    

## range sum

        public class RangeSum
        {
        
           public static void main(String[] args)
           {
              int[] numbers = {1, 2, 3, 4, 5, 6, 7, 8, 9};
              
              System.out.print("The sum of elements 2 through " +
                               "5 is "+ rangeSum(numbers, 3, 5));
           }
           
      public static int rangeSum(int[] array, int start, int end)
       {
          if (start > end)
             return 0;
          else
             return array[start] +
                        rangeSum(array, start + 1, end);
       }
    }

   
# Sum of all the factors of a number

Given a number n, the task is to find the sum of all the divisors.

**Examples :**

    Input : n = 30
    Output : 72
    Dividers sum 1 + 2 + 3 + 5 + 6 + 
                 10 + 15 + 30 = 72 
    
    Input :  n = 15
    Output : 24
    Dividers sum 1 + 3 + 5 + 15 = 24

implementation

    import java.io.*;  
      
    class GFG { 
      
        // Function to calculate sum of all  
        //divisors of a given number 
        static int divSum(int n) 
        { 
            // Final result of summation  
            // of divisors 
            int result = 0; 
          
            // find all divisors which divides 'num' 
            for (int i = 2; i <= Math.sqrt(n); i++) 
            { 
                // if 'i' is divisor of 'n' 
                if (n % i == 0) 
                { 
                    // if both divisors are same 
                    // then add it once else add 
                    // both 
                    if (i == (n / i)) 
                        result += i; 
                    else
                        result += (i + n / i); 
                } 
            } 
          
            // Add 1 and n to result as above loop 
            // considers proper divisors greater 
            // than 1. 
            return (result + n + 1); 
              
        } 
          
        // Driver program to run the case 
        public static void main(String[] args) 
        { 
            int n = 30; 
            System.out.println(divSum(n)); 
        } 
    } 
      
       
       public static int rangeSum(int[] array, int start, int end)
       {
          if (start > end)
             return 0;
          else
             return array[start] +
                        rangeSum(array, start + 1, end);
       }
    }

## Twin Prime Numbers

A Twin prime are those numbers which are prime and having a difference of two ( 2 ) between the two prime numbers. In other words, a twin prime is a prime that has a prime gap of two.


The first few twin prime pairs are :

(3, 5), (5, 7), (11, 13), (17, 19), (29, 31), 
(41, 43), (59, 61), (71, 73), (101, 103), 
(107, 109), (137, 139), …etc.
FACT : There are 409 Twin primes below 10, 000.

Every twin prime pair except (3, 5) is of the form (6n – 1, 6n + 1) for some natural number n; that is, the number between the two primes is a multiple of 6.

    Examples :
    
    Input : n1 = 11, n2 = 13
    Output : Twin Prime
    
    Input : n1 = 23, n2 = 37
    Output : Not Twin Prime

algo 

     class GFG { 
          
           
            static boolean isPrime(int n)  
            { 
                
                if (n <= 1) return false; 
                if (n <= 3) return true; 
          
               
                if (n % 2 == 0 || n % 3 == 0)  
                    return false; 
          
                for (int i = 5; i * i <= n; i = i + 6) 
                    if (n % i == 0 || n % (i + 2) == 0) 
                        return false; 
          
                return true; 
            } 
          
           
            static boolean twinPrime(int n1, int n2)  
            { 
                return (isPrime(n1) && isPrime(n2) && 
                             Math.abs(n1 - n2) == 2); 
            } 
          
           
            public static void main(String[] args)  
            { 
                int n1 = 11, n2 = 13; 
          
                if (twinPrime(n1, n2)) 
                    System.out.println("Twin Prime"); 
                else
                    System.out.println("Not Twin Prime"); 
            } 
        } 

## Print all possible combinations of r elements in a given array of size n

Given an array of size n, generate and print all possible combinations of r elements in array. For example, if input array is {1, 2, 3, 4} and r is 2, then output should be {1, 2}, {1, 3}, {1, 4}, {2, 3}, {2, 4} and {3, 4}.

     class Combination { 
          
          
            static void combinationUtil(int arr[], int data[], int start, 
                                        int end, int index, int r) 
            { 
                
                if (index == r) 
                { 
                    for (int j=0; j<r; j++) 
                        System.out.print(data[j]+" "); 
                    System.out.println(""); 
                    return; 
                } 
          
               
                for (int i=start; i<=end && end-i+1 >= r-index; i++) 
                { 
                    data[index] = arr[i]; 
                    combinationUtil(arr, data, i+1, end, index+1, r); 
                } 
            } 
          
           
            static void printCombination(int arr[], int n, int r) 
            { 
                
                int data[]=new int[r]; 
                combinationUtil(arr, data, 0, n-1, 0, r); 
            } 
          
           
            public static void main (String[] args) { 
                int arr[] = {1, 2, 3, 4}; 
                int r = 4; 
                int n = arr.length; 
                printCombination(arr, n, r); 
            } 
        } 

 
    
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
      



