     public static  boolean isTwin(String str1,String str2)
       {
          byte[] tab1=str1.toLowerCase().getBytes();
          byte[] tab2=str2.toLowerCase().getBytes();
          
          Arrays.sort(tab1);
          Arrays.sort(tab2);
          return (new String(tab1).equals(new String(tab2)));
       }
