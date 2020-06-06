## Linked List

    public class Main {
    
        Node head;
        
        public static class Node{
            
            int data;
            Node next;
    
            public Node(int data) {
                this.data = data;
                this.next =null;
                        
            }
        }            
     
            public static void main(String[] args) {
                Main m=new Main();
                m.head=new Node(1);
                
                m.head.next=new Node(2);
                m.head.next.next=new Node(3);
                m.head.next.next.next=new Node(4);
                m.head.next.next.next.next=new Node(5);
                
                m.display(m.head);
                System.err.println(""+m.searchNode(m.head, 3));
                System.err.println(""+m.searchNode(m.head, 6));
            }
    }

## Search Node

       
    public boolean searchNode(Node head,int value)
    {
        if (head==null) {
            return false;
        }
        if (head.data==value) {
            return true;
        }
       return  searchNode(head.next, value);
    }

## Display

    public void display(Node head)
    {
        
        if (head==null) {
            return;
        }
        System.err.println(""+head.data);
        display(head.next);
        
    }
