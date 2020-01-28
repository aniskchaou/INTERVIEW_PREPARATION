## Duplicate

     public static boolean hasDuplicate(int[] a)
        {
            boolean duplicate = false;
            
            for (int i = 0; i < a.length; i++) {
                for (int j = i+1; j < a.length; j++) {
                    if (a[i]==a[j]) {
                        duplicate= true;
                        break;
                    }
                }
            }
            return duplicate;
        }
