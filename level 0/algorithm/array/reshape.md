 public static String reshape(int n, String str) {
    
            //replace each space with empty string
            str = str.replace(" ", "");
    
            //insert a '\n' character each n characters
            String res = "";
    
            for (int i = 0; i < str.length(); i++) {
    
                if (i % n == 0 && i != 0) {
                    res = res + '\n' + str.charAt(i);
                } else {
                    res += str.charAt(i);
                }
    
            }
    
            return res;
    
        }