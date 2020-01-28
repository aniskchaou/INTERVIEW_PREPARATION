## inverser une chaine


            String chaine = "hello world";
            char[] inputStringArray = chaine.toCharArray();
            String reverseString = "";
    
            for (int i = inputStringArray.length - 1; i >= 0; i--) {
                reverseString += inputStringArray[i];
            }
    
            System.err.println("" + reverseString);
## inverser une phrase


 

     String chaine = "I love Java Programming"; 
            String[] temp = chaine.split(" ");
            String result = ""; 
      
    
            for (int i = 0; i < temp.length; i++) {
                
                if (i == temp.length - 1) 
                    result = temp[i] + result; 
                else
                    result = " " + temp[i] + result; 
            } 
            
            System.out.println(result);

## find reverse of a string

     public static void main(String[] args) {
            String string = "Dream big";
            //Stores the reverse of given string
            String reversedStr = "";
    
            //Iterate through the string from last and add each character to variable reversedStr
            for (int i = string.length() - 1; i >= 0; i--) {
                reversedStr = reversedStr + string.charAt(i);
            }
    
            System.out.println("Original string: " + string);
            //Displays the reverse of given string
            System.out.println("Reverse of given string: " + reversedStr);
        }

            