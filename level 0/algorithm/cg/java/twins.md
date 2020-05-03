     public static  boolean isTwin(String str1,String str2)
       {
          //convert to byte arrays
          byte[] tab1=str1.toLowerCase().getBytes();
          byte[] tab2=str2.toLowerCase().getBytes();
          
          //sort arrays
          Arrays.sort(tab1);
          Arrays.sort(tab2);
          
          //reconvert byte arrays to string
          return (new String(tab1).equals(new String(tab2)));
       }
