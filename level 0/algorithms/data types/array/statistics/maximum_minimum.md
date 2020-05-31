## calculer le minimum et maximum


      public static void getMaximumMinimum(int[] tab)
    {
        int max=0;
        int min=tab[0];
        
                for (int i = 0; i < tab.length; i++) {
                    if (tab[i] < min) {
                        min = tab[i];
                    } else if (tab[i] > max) {
                        max = tab[i];
                    }
                }
                
                System.err.println("maximum "+max+" minimum "+min);
    }
    
    public static void getMaximumMinimum2(int[] tab)
    {
      Arrays.sort(tab);
                
                System.err.println("maximum "+tab[tab.length-1]+" minimum "+tab[0]);
    }
    
  
