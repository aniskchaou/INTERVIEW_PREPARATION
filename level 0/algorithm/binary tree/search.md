

## Search Node

    public void searchNode(Node head,int value)
        {  boolean search=false;
            
            if(head==null)
            {
                System.err.println("tree is empty");
            }else if (head.data==value) {
                System.err.println(head.data);
                search=true;
               return;
            }
            
            
            if(head.next!=null && search==false)
            {
                searchNode(head.next,value);
            }
            
            if(head.prev!=null && search==false){
                searchNode(head.prev,value);
            }
            
            
        }
