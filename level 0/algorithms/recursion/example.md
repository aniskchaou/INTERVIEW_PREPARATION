## Recusion Example

    class Example{
    
        public static void main(String[] args) {
            foo(3);
        }
        
        static void foo(int n)
        {
            if(n<1)
            {    return;}
            else  
            {   foo(n-1);}
            System.err.println(n);
            
        }
    }
