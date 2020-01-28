## Program to swap two numbers

This program is to swap/exchange two numbers by using a variable.

     public  static  void main(String[] args) {
     int x, y, t;  
      t = x;
      x = y;
      y = t;
      System.out.println("After swapping: "+x +" " + y);
     
      }

## Program to swap two numbers without using the third variable



**X= 25** (First number), **Y= 23** (second number)
Swapping Logic:

    X = X + Y = 25 +23 = 48
    Y = X - Y = 48 - 23 = 25
    X = X -Y = 48 - 25 = 23

and the numbers are swapped as X =23 and Y =25. 

  

                int x = 25;
                int y = 23;
                x = x + y;
                y = x - y;
                x = x - y;
                System.out.println("After swapping: " + x + " " + y);


