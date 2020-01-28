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

