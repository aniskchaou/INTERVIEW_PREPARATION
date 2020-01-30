## Display

**output**

    0
    1
    4
    5
    2
    6
    3

**algorithm**

     void display(Node head)
        {
            if(head==null)
            {
                return;
            }
            
            System.err.println(""+head.data);
            
            if(head.next!=null)
            {
                display(head.next);
            }
            
            if(head.prev!=null){
                display(head.prev);
            }
        }
