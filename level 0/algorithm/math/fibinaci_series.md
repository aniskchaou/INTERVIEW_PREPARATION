

## series de fibinacci
**idea**

    fonction fib(nombre)
     si n<2 lors
       retourner nombre
     sinon 
     retourner fib(nombre-2) + fib(nombre-1)  

**algo**
  

     public static int printFibonacci(int n) {
            if (n < 2) {
                return (n);
            }
            return (printFibonacci(n - 2) + printFibonacci(n - 1));
        }
