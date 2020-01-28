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