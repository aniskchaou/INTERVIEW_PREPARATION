
## Program to swap two numbers



     public  static  void main(String[] args) {
     int x, y, t;  
      t = x;
      x = y;
      y = t;
      System.out.println("After swapping: "+x +" " + y);
     
      }

## swap two numbers without using the third variable

**X= 25** (First number), **Y= 23** (second number)
Swapping Logic:


  

                int x = 25;
                int y = 23;
                x = x + y;
                y = x - y;
                x = x - y;
                System.out.println("After swapping: " + x + " " + y);


