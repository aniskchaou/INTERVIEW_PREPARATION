Range sum
input

a= {4, 5, 6,5, 4}
begin = 2
end = 4
output

15
algorithm

     static int rangeSum(int start,int end,int[] tab)
        {
            int sum=0;
            for (int i = 0; i < tab.length; i++) {
                if (i>=start && i<=end) {
                    sum+=tab[i];
                }
            }
            
            return sum;
        }
