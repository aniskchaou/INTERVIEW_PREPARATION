
## Program to print the permutation (nPr) of the given number

### Permutation

It is an ordered-arrangement/combination of a set of things or collection of objects.

For example, we have a set of letters A, B, and C.....describing permutations as n distinct objects taken r at a time.

**Permutation of a list of n elements:**

1.  n!= n (n-1)(n-2)(n-3)....3.2.1
2.  nPr = n!/ (n-r)! =n(n-1) (n-2)(n-3).....(n-r+1)
**implementation**

   

     1.  public  static  void main(String[] args)
        2.  {
        3.  int n, r, per, fact1, fact2;
        4.  Scanner sc = new Scanner(System.in);
        5.  System.out.println("Enter the Value of n and r?");
        6.  n = sc.nextInt();
        7.  r = sc.nextInt();
        8.  fact1 = n;
        9.  for (int i = n - 1; i >= 1; i--)
        10.  {
        11.  fact1 = fact1 * i;
        12.  }
        13.  int number;
        14.  number = n - r;
        15.  fact2 = number;
        16.  for (int i = number - 1; i >= 1; i--)
        17.  {
        18.  fact2 = fact2 * i;
        19.  }
        20.  per = fact1 / fact2;
        21.  System.out.println("nPr = "+per);
        22.  }






