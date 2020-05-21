    public class Main {
    
        Node head;
        
        public static class Node{
            Node next;
            Node prev;
            int data;
    
            public Node(int data) {
                this.next = null;
                this.prev = null;
                this.data = data;
            }
        }   
            
            public static void main(String[] args) {
                Main m=new Main();
                m.head=new Node(0);
                
                
                m.head.next=new Node(1);
                m.head.prev=new Node(2);
                
                m.head.next.next=new Node(4);
                m.head.next.prev=new Node(5);
                
                m.head.prev.prev=new Node(3);
                m.head.prev.next=new Node(4);
            }
            
        
       
    
       
    
    }