## number of punctuation 

**Input:**

    "Good Morning! Mr. James Potter. Had your breakfast?"

**Output:**

     4

 **Algorithm**

       public static int numberPonctuation(String str)
    {
           
                int count= 0;
               
                for (int i = 0; i < str.length(); i++) {
                   
                    if (str.charAt(i) == '!' || str.charAt(i) == ',' || str.charAt(i) == ';' || str.charAt(i) == '.' || str.charAt(i) == '?' || str.charAt(i) == '-'
                            || str.charAt(i) == '\'' || str.charAt(i) == '\"' || str.charAt(i) == ':') {
                        count++;
                    }
                }
               return count;
    }

