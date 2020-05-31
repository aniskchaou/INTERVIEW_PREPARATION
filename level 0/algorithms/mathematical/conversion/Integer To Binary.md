## IntegerToBinary

**input** 

    8

**Output** 

    1000

**Algorithm**


    public static String convert2binary(int n)
    {
        List binaryDigits=new ArrayList<Integer>();
        int rest=0;
        StringBuilder digitNumber=new StringBuilder("");   
       
        while (n!=0) {        
            rest=n%2;
            binaryDigits.add(rest);
            n/=2;
        }
       
        for (int i = 0; i < binaryDigits.size(); i++) {
            digitNumber.append(binaryDigits.get(i).toString());
        }
        
        return digitNumber.reverse().toString();
    }
